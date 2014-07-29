Router That Works
===
A Javascript client side URL router.

Usage
===
Add it to your HTML -

    <script type="text/javascript" src="/location/to/routerthatworks.js"></script>

Then url routers with RegExp url matching rules -

    var router = new RouterThatWorks({
        '/page/one': showPageOne,
        '/page/(\\d+)': showPageAnyNumber,
        '/user/(\\w+)': function(args, query_params) {
            console.log(args);
        },
    })
    router.init();

Each router function will receive two params -

`args` is an Array. The first element is the whole hash and rest are matching groups from the regex

`query_params` is an object. If you request something like -

    http://example.com/#/user/john?foo=bar

then `query_params` will be `{'foo': 'bar'}`.
