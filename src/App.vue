<template>
  <div id="app">
    <div>
      <md-layout md-gutter class="margin-top-20">
        <md-layout md-align="center">
          <md-card>
                  <md-column md-align="center">
                    <md-list class="width-fix" >
                      <md-list-item disabled>
                        <a href="#">drie</a>
                        <span class="fr">
                          <a href="#">docs</a>
                          |
                          <a href="#">support</a>
                          |
                          <md-menu>
                            <a href="#" md-menu-trigger>ben@ACME</a>

                            <md-menu-content>
                              <md-menu-item>Item 1</md-menu-item>
                              <md-menu-item>Logout</md-menu-item>
                            </md-menu-content>
                          </md-menu>
                        </span>
                      </md-list-item>
                    </md-list>

                    <md-list class="width-fix">
                      <md-list-item>
                        <md-switch class="md-primary" v-model="check1"></md-switch>
                        <span><a href="#">martin-drie-signup-flow</a></span>
                        <md-icon></md-icon>
                      </md-list-item>

                      <md-list-item >
                        <md-switch class="md-primary" v-model="check2"></md-switch>
                        <span><a href="#">martin-drie-signup-flow</a></span>

                        <md-list-expand>
                          <md-list>
                            <md-list-item class="md-inset">Some content</md-list-item>
                          </md-list>
                        </md-list-expand>

                      </md-list-item>

                      <md-list-item class="md-active">
                        <md-switch class="md-primary" v-model="check3"></md-switch>
                        <span><a href="#">demo-starter-app</a></span>

                        <md-list-expand>
                          <md-list>
                            <md-list-item class="md-inset">

                              <table class="full-width">
                                <tr>
                                  <td><a href="#">master</a></td>
                                  <td><a href="#">visit</a></td>
                                  <td>2 instances</td>
                                </tr>
                                <tr>
                                  <td><a href="#">todays-news</a></td>
                                  <td><a href="#">visit</a></td>
                                  <td>on demand</td>
                                </tr>
                                <tr>
                                  <td><a href="#">feature-make-app-more-simple</a></td>
                                  <td><a href="#">visit</a></td>
                                  <td>on demand</td>
                                </tr>
                              </table>

                            </md-list-item>
                          </md-list>
                        </md-list-expand>

                      </md-list-item>


                      <md-list-item>
                        <md-switch class="md-primary" v-model="check4"></md-switch>
                        <span><a href="#">demo-rails-postgres</a></span>

                        <md-list-expand>
                          <md-list>
                            <md-list-item class="md-inset">Some content</md-list-item>
                          </md-list>
                        </md-list-expand>

                      </md-list-item>

                    </md-list>


                  </md-column>
          </md-card>
        </md-layout>
      </md-layout>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'app',
    data () {
      return {
        check1: false,
        check2: true,
        check3: true,
        check4: false
      }
    }

  }
</script>

<style>
  body {
    background-color: #e1e4e8 !important;
  }
  .margin-top-20{
    margin-top: 20px;
  }
  .width-fix {
    width: 700px
  }

  .full-width {
    width:100%;
  }
  .fr {
    float: right;
  }

  .inline {
    display: inline;
  }

</style>
