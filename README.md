## Synopsis

A VueJS wrapper for [Bootstrap Toggle](https://github.com/minhur/bootstrap-toggle).

## Installation

`npm install --save vue-bootstrap-toggle`

## Usage

```VueJS
<template>
  <div>
    <label>
      <bootstrap-toggle v-model="checked" :options="{ on: 'Yes', off: 'No' }"/>
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

## Troubleshooting

If the switches render correctly,
but do not toggle when you click,
make sure no bootstrap-toggle.js is loaded in the html,
but only through the webpack/etc compiler.
(since else it will instantly toggle 2 times, resulting in no visual change)
