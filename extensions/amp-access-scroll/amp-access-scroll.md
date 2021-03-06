---
$category@: dynamic-content
formats:
  - websites
teaser:
  text: Integrates wth Scroll, a better internet that doesn't rely on ads.
---

<!---
Copyright 2020 The AMP HTML Authors. All Rights Reserved.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

      http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS-IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
-->

# amp-access-scroll

Lets sites in the <a href="https://scroll.com">Scroll</a> network identify Scroll members in order to serve them an ad-free, directly-monetized experience.

<table>
  <tr>
    <td class="col-fourty"><strong>Required Scripts</strong></td>
    <td>
      <div>
        <code>&lt;script async custom-element="amp-access" src="https://cdn.ampproject.org/v0/amp-access-0.1.js">&lt;/script></code>
      </div>
      <div>
        <code>&lt;script async custom-element="amp-analytics" src="https://cdn.ampproject.org/v0/amp-analytics-0.1.js">&lt;/script></code>
      </div>
      <div>
        <code>&lt;script async custom-element="amp-access-scroll" src="https://cdn.ampproject.org/v0/amp-access-scroll-0.1.js">&lt;/script></code>
      </div>
    </td>
  </tr>
</table>

[TOC]

## Behavior

### Configure

In `<head>`, add

```
<script id="amp-access" type="application/json">
{
  "vendor": "scroll",
  "namespace": "scroll"
}
</script>
```

Be sure not to add a trailing comma to the namespace line, which makes it invalid JSON!

If you are already using `amp-access` for a paywall, follow the steps in the `amp-access` documentation for [using namespaces and an array of providers](https://amp.dev/documentation/components/amp-access#multiple-access-providers).

### Make each ad conditional

Add an `amp-access` attribute to each ad container.

```
<div class="amp-ad-container" amp-access="NOT scroll.scroll">
  <amp-ad... >
</div>
```

Learn more at https://developer.scroll.com/amp

## Validation

See [amp-access-scroll rules](https://github.com/ampproject/amphtml/blob/master/extensions/amp-access-scroll/validator-amp-access-scroll.protoascii) in the AMP validator specification.
