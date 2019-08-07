<template>
<div>
    <b-navbar toggleable="md" type="dark" variant="info">
    
    <b-collapse id="nav-collapse" is-nav>
      

      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
        
        <b-nav-item-dropdown right>
          <!-- Using 'button-content' slot -->
          
          <template slot="button-content"><b-img v-bind="mainProps" rounded="circle" alt="Circle image"></b-img></template>
          <b-dropdown-item href="#">Extra</b-dropdown-item>
        </b-nav-item-dropdown>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</div>
</template>

<script>
export default {
    name:'Navbar',
    data() {
      return {
        mainProps: { blank: true, blankColor: '#777', width: 25, height: 25, class: 'm1' }
      }
    }
}
</script>

