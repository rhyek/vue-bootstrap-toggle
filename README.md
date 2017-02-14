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
