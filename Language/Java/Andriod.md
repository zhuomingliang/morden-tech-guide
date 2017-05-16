From: https://yalantis.com/blog/list-of-best-frameworks-for-android-app-development/

A Full List of the Best Frameworks for Building Android Apps

You may have heard scary stories about how much more time it takes – and how much more expensive it is – to develop an Android app than to develop an iOS app.  But in fact, this is not quite true. With plenty of frameworks available, modern-day Android app development doesn’t take much longer than iOS app development.
We’ll walk you through the best Android frameworks that we use frequently here at Yalantis. These frameworks help us develop better and faster. We’ve divided them into four categories: open source, standard Google frameworks, paid frameworks, and our own Yalantis solutions for developing Android apps. Let’s take a look.
Open source frameworks

There’s a common saying that quality doesn’t come cheap - but actually most of the frameworks we work with are open source and free.

Architecture framework:

ReactiveX https://github.com/ReactiveX/RxJava. You can’t get around functional programming when you develop an app. ReactiveX is a framework that combines Observer pattern, iterator pattern and functional programming all in one. It’s a core framework that makes it easy to combine frontend and backend, and ReactiveX is available for most platforms. We use this framework in all of our Android projects.

Mobile database:

Realm https://realm.io/news/realm-for-android/ is a powerful framework for mobile databases. It can replace the heavy and cumbersome SQLite, and is much simpler and faster. Realm promises to save weeks of app development time. As an added bonus, search speeds with Realm are much faster than with other database frameworks. From the point of view of user experience, this means a faster, more agile app. We think that Realm is a really good framework for Android app development and use Realm in practically every project.

Backend interaction:

Retrofit http://square.github.io/retrofit/ is a client-server framework for exchanging data between an app and a backend server. Retrofit is much easier to work with than its alternatives such as Google’s Volley library.    

Data binding

We use data binding to save time. Here are frameworks that help us achieve this:

Butter knife http://jakewharton.github.io/butterknife/ offers simple field and method binding for Android views.

Android Data Binding http://developer.android.com/tools/data-binding/guide.html is similar to Butter Knife, only in addition to binding, Android Data Binding also lets you move UI logic to XML. This makes code more readable and simplifies the development process. 

Crash supporting:

Crashlytics https://try.crashlytics.com/ is a framework for crash reports. It works in real time, delivering detailed reports on all crashes. Moreover it also provides information on which issues that are the most important to fix. With the aid of Crashlytics data, you can immediately address problems to make your app work seamlessly. Crashlytics is very easy to implement and doesn’t slow your app down, nor does it crowd the app with unnecessary data. Crashlytics also offers support for native crashes and errors. Crashes can and do occur in any and every app. That’s why Crashlytics should be a core framework for all Android apps.   

Payment frameworks:

Braintree https://www.braintreepayments.com/ is a popular framework that was acquired by PayPal several years ago. It covers all popular payment systems, such as PayPal, Apple Pay, Android Pay, Venmo, and Bitcoin. The Braintree SDK is available in open source, but you’ll have to pay for the transactions made through your app. Braintree can be used in any app that manages transactions. For example, money transfer apps, travel apps, on-demand delivery apps, and shopping apps.

Stripe https://stripe.com/: Like Braintree, Stripe is  a framework for money transactions. Though Braintree and Stripe offer similar functionality, some argue that Stripe is easier to integrate and offers greater flexibility for recurring billings. Both Stripe and Braintree can accept transactions from any country, but availability of their services does depend on the country your business is based in. In this regard, Braintree supports far more countries than Stripe. Moreover, Braintree has a quicker settlement period of only  2-4 days compared to Stripe’s 7 days.

Images loaders:

Picasso http://square.github.io/picasso/ is an image loader that displays and caches pictures in a smartphone’s memory. Image loaders are used in all apps that work with pictures, such as photo editing apps, social apps, dating apps, shopping apps, or any other app that includes even just a personal profile with a profile picture.     

Fresco http://frescolib.org/ was developed by Facebook. It’s a very powerful library that loads pictures faster than Picasso and doesn’t slow down the app in the process. We have used Fresco in our latest projects for this reason.

Social media:

Facebook SDK https://developers.facebook.com/products/ offers many different features; Facebook login, sharing, graph API, app links, app invites, ads, and audience networks. Facebook SDK adds marketing value to your app. If you want to take advantage of Facebook SDK’s potential marketing value, then take a look at our article about how to market and promote your app with Facebook SDK.

Twitter SDK https://dev.twitter.com/overview/api/twitter-libraries offers similar features to Facebook SDK: Twitter login, sharing, analytics, links, and ads. Most apps use Facebook login as more people have Facebook accounts than have Twitter accounts. However, Twitter SDK offers more than just login functionality. It also makes it easier to share in-app content through Tweets.

Standard Google Frameworks

Since Android is powered by Google, the frameworks Google offers to app developers are quite useful: 

Google play services https://developers.google.com/android/guides/overview is a very broad framework containing Google-powered features such as Maps, login with Google+, location, app invites, and ads. This framework updates automatically through the Google Play Store, so it’s very easy to maintain. Since the functionality is so broad, it’s possible to use Google Play Services in most apps.

Google analytics https://developers.google.com/analytics/devguides/collection/android/v4/#set-up-your-project is used to gather information about user behavior. With Google Analytics you can measure your app’s success, tailor the app to your users’ needs and improve your product strategy.  

Google support http://developer.android.com/intl/ru/tools/support-library/index.html library assures compatibility. When developing an app, you’ll naturally use a modern UI that supports the latest Android version. However, your  UI might not support older versions of Android. That’s what Google’s support library is for. With the help of Google support library, you can make a new UI compatible with older versions of Android. This lets you make your app available to the largest number of users. 

Paid frameworks

Unfortunately, not all excellent frameworks are available as open source. The paid frameworks we most frequently use are for app analytics. While Google Analytics is free, it’s not the best analytics framework for mobile apps. It works better for websites. We suggest that our clients use one of the following two services for 
analytics:

Mixpanel analytics https://mixpanel.com/ gives basic functionality for free. But at some point, you will need to upgrade to a premium version. Unlike Google Analytics, Mixpanel tracks events instead of page views. You can use Mixpanel to track an individual moving from step to step in a funnel.  

Flurry analytics http://www.flurry.com/, made by Yahoo, allows you to track in-app user actions to understand and visualize usage trends. Some will argue that Mixpanel has more convenient conversion funnels that Flurry, but we’d say it’s a matter of taste.        


It’s great to save time by using pre-built frameworks, but sometimes existing solutions don’t meet our demands. In this case, we develop our own solutions for internal use by our team. Sometimes we even make these solutions open source to help other Android developers build their apps. Our latest libraries include:
Template Android is very useful, but not yet available for anyone outside of Yalantis. It’s based on MVP architecture, and we use it to store base classes, libraries, implementations and managers. It’s a core framework that we use in most of our projects.

uCrop https://github.com/Yalantis/uCrop is our open source image cropping library. It can be used in photo-editing apps, or in any app that provides a user profile where a profile picture is needed. You can read more about uCrop here.

Horizon https://yalantis.com/blog/horizon-open-source-library-for-sound-visualization/ is our open source, simple visual equaliser for Android. You can check out our demo on Google Play and read our article on the blog.
You can check out more Yalantis libraries on Github.  

As you can see, there are plenty of frameworks that can help you develop Android apps much faster and cheaper than you probably thought. We told you about some of the best frameworks for Android app development. So what are you waiting for? The Android market with its extensive user potential waits!  