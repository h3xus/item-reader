<template>
    <div>
        <button class="button" :id="uuid"  type="button">{{title}}</button>
    </div>
</template>
<script>
export default {
  name: 'RoundButton',
  props: {
    'uuid': String,
    'title': String
  }
}
</script>

<style>
.button {
  font-family: 'DM Serif Display', serif;
  background: none;
  text-decoration: none;
  display: inline-block;
  color: #fff;
  font-size: 1.5em;
  line-height: 1.2;
  padding: 0.375em 1em;
  border-radius: 1.25em;
  min-width: 1.25em;
  text-align: center;
  font-weight: normal;
  border: none;
  position: relative;
  vertical-align: middle;
  z-index: 3;
  overflow: hidden;
}
.button:before {
  border-radius: 1.25em;
  content: "";
  position: absolute;
  z-index: -2;
  transition: all 0.3s;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  background: linear-gradient(to right, #a7cfdf 0%, #23538a 100%);
  /* W3C */
}
.button:after {
  border-radius: 1.25em;
  content: "";
  position: absolute;
  z-index: -1;
  transition: all 0.3s;
  width: 0;
  height: 100%;
  top: 0;
  left: 0;
  background: linear-gradient(to right, #23538a 0%, #a7cfdf 100%);
  /* W3C */
}
.button:hover, .button:active, .button:focus {
  cursor: pointer;
}
.button:hover:after, .button:active:after, .button:focus:after {
  width: 100%;
}
</style>
