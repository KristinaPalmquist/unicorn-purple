<script setup></script>

<template>
  <details name="exclusive">
      <summary>Section 1</summary>
      <main>
        <p>
          Mauris mauris ante, blandit et, ultrices a, suscipit eget, quam.
          Integer ut neque. Vivamus nisi metus, molestie vel, gravida in,
          condimentum sit amet, nunc. Nam a nibh. Donec suscipit eros. Nam mi.
          Proin viverra leo ut odio. Curabitur malesuada. Vestibulum a velit eu
          ante scelerisque vulputate.
        </p>
      </main>
    </details>

    <details name="exclusive">
      <summary>Section 2</summary>
      <main>
        <p>
          Sed non urna. Donec et ante. Phasellus eu ligula. Vestibulum sit amet
          purus. Vivamus hendrerit, dolor at aliquet laoreet, mauris turpis
          porttitor velit, faucibus interdum tellus libero ac justo. Vivamus non
          quam. In suscipit faucibus urna.
        </p>
      </main>
    </details>

    <details name="exclusive">
      <summary>Section 3</summary>
      <main>
        <p>
          Nam enim risus, molestie et, porta ac, aliquam ac, risus. Quisque
          lobortis. Phasellus pellentesque purus in massa. Aenean in pede.
          Phasellus ac libero ac tellus pellentesque semper. Sed ac felis. Sed
          commodo, magna quis lacinia ornare, quam ante aliquam nisi, eu iaculis
          leo purus venenatis dui.
        </p>
        <ul>
          <li>List item one</li>
          <li>List item two</li>
          <li>List item three</li>
        </ul>
      </main>
    </details>

    <details name="exclusive">
      <summary>Section 4</summary>
      <main>
        <p>
          Cras dictum. Pellentesque habitant morbi tristique senectus et netus
          et malesuada fames ac turpis egestas. Vestibulum ante ipsum primis in
          faucibus orci luctus et ultrices posuere cubilia Curae; Aenean lacinia
          mauris vel est.
        </p>
        <p>
          Suspendisse eu nisl. Nullam ut libero. Integer dignissim consequat
          lectus. Class aptent taciti sociosqu ad litora torquent per conubia
          nostra, per inceptos himenaeos.
        </p>
      </main>
    </details>

</template>

<style scoped>
details {
  interpolate-size: allow-keywords;
  overflow: clip;
  margin-top: 0.125em;
  border: 1px solid #dddddd;
  background: #ffffff;
  color: #333333;
  border-radius: 3px;
}

details summary {
  display: block;
  cursor: pointer;
  position: relative;
  padding: 0.5em 0.5em 0.5em 0.7em;
  background: #ededed;
  color: #2b2b2b;
  border-radius: 3px 3px 0 0;
}

details:not([open]) summary:hover,
details:not([open]) summary:focus {
  background: #f6f6f6;
  color: #454545;
}

details[open] summary {
  outline: 1px solid #003eff;
  background: #007fff;
  color: #ffffff;
}

details[open]::details-content {
  height: auto;
}

details::details-content {
  height: 0;
  overflow-y: clip;
  transition: content-visibility 475ms allow-discrete, height 475ms;
}

details main {
  padding: 1em 2.2em;
}
</style>
