This call sends information that you have specified about the user to Amazon Pinpoint. This could be for an unauthenticated or an authenticated user.

You can get the current user's ID from the Amplify Auth category as shown below. Be sure you have it added and setup per the Auth category documentation.

If you have asked for location access and received permission, you can also provide that in `UserProfile.Location`.

<amplify-block-switcher>
<amplify-block name="Java">

```java
UserProfile.Location location = UserProfile.Location.builder()
    .latitude(47.606209)
    .longitude(-122.332069)
    .postalCode("98122")
    .city("Seattle")
    .region("WA")
    .country("USA")
    .build();

UserProfile profile = UserProfile.builder()
    .location(location)
    .name("name")
    .email("name@email.com")
    .build();

String userId = Amplify.Auth.getCurrentUser().getUserId();

Amplify.Analytics.identifyUser(userId, profile);
```

</amplify-block>
<amplify-block name="Kotlin">

```kotlin
val location = UserProfile.Location.builder()
    .latitude(47.606209)
    .longitude(-122.332069)
    .postalCode("98122")
    .city("Seattle")
    .region("WA")
    .country("USA")
    .build()

val profile = UserProfile.builder()
    .location(location)
    .name("name")
    .email("name@email.com")
    .build()

val userId = Amplify.Auth.getCurrentUser().getUserId()

Amplify.Analytics.identifyUser(userId, profile)
```

</amplify-block>
<amplify-block name="RxJava">

```java
UserProfile.Location location = UserProfile.Location.builder()
    .latitude(47.606209)
    .longitude(-122.332069)
    .postalCode("98122")
    .city("Seattle")
    .region("WA")
    .country("USA")
    .build();

UserProfile profile = UserProfile.builder()
    .location(location)
    .name("name")
    .email("name@email.com")
    .build();

String userId = RxAmplify.Auth.getCurrentUser().getUserId();

RxAmplify.Analytics.identifyUser(userId, profile);
```

</amplify-block>
</amplify-block-switcher>
