# http queue Angular Module http-queue #

A simple Angular middleware service that can be used to queue http requests.

## How to get it ##

Install with bower:

	bower install http-queue --save


Include the angular module: 'http.queue' in your application dependencies and httpQueueService as a service provider.


## How to use it

    httpQueueService.add(callback, options);

    httpQueueService.add(useThisFunction, {timeout: 1000, groupingId:'myCustomQueue'}});

    // use function with params

   httpQueueService.add(function(){updateCart(product,qty),{timeout:300, groupingId:'myCustomQueue'}}


Options is an optional param and callback is a function that will be invoked when it should leave the queue. So you can pass config each time you add something to queue, but you may configure the queue for all requests:

    //method signature
    httpQueueService.configure(config, queueId);

    //i.e. for default queue
    httpQueueService.configure({timeout: 1000});

    //for some custom queue
    httpQueueService.configure({timeout: 1000}, 'myCustomQueue');
