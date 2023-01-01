<script>
export default {
  name: "Lifecycle Hooks",
  beforeCreate() {
    // this fires even before the component is fully created
    // And it's at the very start of its initialization.
    // CANNOT access any DATA from data object or any template elements yet.
  },
  created() {
    // this fires when the component is created BUT not yet mounted to the DOM.
    // we CAN access DATA but still CANNOT access the template
  },

  // ---- then it starts to compile the TEMPLATE

  beforeMount() {
    //this fires after the template is compiled
    //the point, just before the component is mounted to the DOM.
    // In here we CAN acces all DATA, EVENTS and TEMPLATES.
  },

  // ---- after beforeMount hook, vue mounts the component to the DOM

  mounted() {
    //this fires when the component is MOUNTED to the DOM.
    // popular place to make fetch requests
  },
  beforeUpdate() {
    // this fires when data inside component changes.
    // this happens AFTER the DATA change but BEFORE the changed data (updates) is re-rendered to the DOM.
  },
  // ---- virtual DOM re-renderes and patch
  updated() {
    // this fires after all the changed data (updates) is re-rendered and reflected in the browser.
  },

  // ---- when the component is no longer needed on the screen, its removed.

  beforeUnmount() {
    // this fires BEFORE the component is removed (unmounted) from the DOM
    // When this hook is called, the component is still fully functional.
  },
  unmounted() {
    // this fires AFTER the component is removed from the DOM
    // A component is considered unmounted after: all of its child components have been unmounted, all of its associated reactive effects have been stopped.
  },
};
</script>