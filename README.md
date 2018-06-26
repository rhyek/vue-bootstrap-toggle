## Synopsis

A VueJS wrapper for [Bootstrap Toggle](https://github.com/minhur/bootstrap-toggle).

## Prerequisites

* `jquery`
* `bootstrap` 3

## Installation

`npm install --save vue-bootstrap-toggle`

## Usage

```VueJS
<template>
  <div>
    <label>
      <bootstrap-toggle v-model="checked" :options="{ on: 'Yes', off: 'No' }" :disabled="false" />
    </label>
  </div>
</template>

<script>
import BootstrapToggle from 'vue-bootstrap-toggle'

export default {
  components: { BootstrapToggle },
  data() {
    return {
      checked: true
    }
  }
}
</script>
```

## Troubleshooting

If the switches render correctly,
but do not toggle when you click,
make sure `bootstrap-toggle.js` isn't loaded somewhere in your HTML.
