@fedify/h3: Integrate Fedify with h3
====================================

This package provides a simple way to integrate [Fedify] with [h3].
The integration code looks like this:

~~~~ typescript
import { createApp, createRouter } from "h3";
import { integrateFederation, onError } from "@fedify/h3";
import { federation } from "./federation";  // Your `Federation` instance

export const app = createApp({ onError });
app.use(
  integrateFederation(
    federation,
    (event, request) => "context data goes here"
  )
);

const router = createRouter();
app.use(router);
~~~~

> [!NOTE]
> Your app has to configure `onError` to let Fedify negotiate content types.
> If you don't do this, Fedify will not be able to respond with a proper error
> status code when a content negotiation fails.

[Fedify]: https://fedify.dev/
[h3]: https://h3.unjs.io/


Changelog
---------

### Version 0.1.0

To be released.
