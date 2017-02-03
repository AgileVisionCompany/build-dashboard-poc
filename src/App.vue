<template>
  <div id="app">
    <div>
      <md-layout md-gutter class="margin-top-20">
        <md-layout md-align="center">
          <md-card>
            <md-column md-align="center">
              <md-list class="width-fix">
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
                <md-list-item @click="listClick(0, $event)">
                  <md-icon></md-icon>
                  <span><a href="#">martin-drie-signup-flow</a></span>
                  <md-switch class="md-primary" v-model="checkState[0]" @change="switchCheck(0)"></md-switch>
                </md-list-item>


                <!-- 1 -->
                <md-list-item @click="listClick(1, $event)" >
                  <md-icon v-if="listState[1]">keyboard_arrow_down</md-icon>
                  <md-icon v-else>keyboard_arrow_right</md-icon>
                  <span><a href="#">martin-drie-signup-flow</a></span>
                  <md-switch class="md-primary" v-model="checkState[1]" @change="switchCheck(1)"></md-switch>

                  <span v-show="listState[1]" class="md-divider"></span>
                </md-list-item>

                <md-list-item v-show="listState[1]">
                  Some content
                  <span class="md-divider"></span>
                </md-list-item>

                <!-- 2 -->
                <md-list-item @click="listClick(2, $event)" >
                  <md-icon v-if="listState[2]">keyboard_arrow_down</md-icon>
                  <md-icon v-else>keyboard_arrow_right</md-icon>
                  <span><a href="#">demo-starter-app</a></span>
                  <md-switch class="md-primary" v-model="checkState[2]" @change="switchCheck(2)"></md-switch>

                  <span v-show="listState[2]" class="md-divider"></span>
                </md-list-item>

                <md-list-item v-show="listState[2]">
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
                  <span class="md-divider"></span>
                </md-list-item>

                <!-- 3 -->
                <md-list-item @click="listClick(3, $event)" >
                  <md-icon v-if="listState[3]">keyboard_arrow_down</md-icon>
                  <md-icon v-else>keyboard_arrow_right</md-icon>
                  <span><a href="#">demo-rails-postgres</a></span>
                  <md-switch type="submit" class="md-primary" v-model="checkState[3]" @change="switchCheck(3, $event)"></md-switch>

                  <span v-show="listState[3]" class="md-divider"></span>
                </md-list-item>

                <md-list-item v-show="listState[3]">
                  Some content
                  <span class="md-divider"></span>
                </md-list-item>

              </md-list>

            </md-column>
          </md-card>
        </md-layout>
      </md-layout>

      <md-dialog md-open-from="#custom" md-close-to="#custom" ref="dialog1">
        <md-dialog-title>Are you sure</md-dialog-title>

        <md-dialog-content>Are you sure?</md-dialog-content>

        <md-dialog-actions>
          <md-button class="md-primary" @click="closeDialog('dialog1')">Cancel</md-button>
          <md-button class="md-primary" @click="closeDialog('dialog1')">Ok</md-button>
        </md-dialog-actions>
      </md-dialog>
    </div>


  </div>
</template>

<script>
  import Vue from 'vue'

  export default {
    name: 'app',
    data () {
      return {
        check1: false,
        check2: true,
        check3: true,
        check4: false,
        listState: [false, true, true, false],
        checkState: [false, true, true, false]
      }
    },
    watch: {
    },
    methods: {
      openDialog (ref) {
        this.$refs[ref].open()
      },
      closeDialog (ref) {
        this.$refs[ref].close()
      },
      listClick (i, event) {
        if (event.toElement.className !== 'md-switch-holder') {
          Vue.set(this.listState, i, !this.listState[i])
        }
      },
      switchCheck (i, event) {
        console.log(event)
       // event.preventDefault()
//        console.log(this.checkState[i])
//        Vue.set(this.checkState, i, false)
//        console.log(this.checkState[i])
        this.openDialog('dialog1')
      }
    }

  }
</script>

<style>
  body {
    background-color: #e1e4e8 !important;
  }

  .margin-top-20 {
    margin-top: 20px;
  }

  .width-fix {
    width: 700px
  }

  .full-width {
    width: 100%;
  }

  .fr {
    float: right;
  }

  .inline {
    display: inline;
  }

</style>
