<template>
  <div>
    <div class="fv-margin-bottom fv-hidden-xs fv-hidden-sm" />
    <div class="content__header fv-margin-bottom fv-padding">
      <div class="fv-padding fv-margin-bottom fv-text-center">
        <Logo />
      </div>
      <p>
        <b>Framevuerk</b> is a Fast, Responsive, Without Dependencies, Both
        Direction Support and Configurable UI Framework based on <b>Vue.js</b>.
        In this template we just add it to <b>Nuxt.js</b> and put some of most
        usable component inside a form to show you how it's look like.
      </p>
    </div>
    <div class="content__body fv-border fv-radius fv-shadow">
      <label class="fv-control-label fv-padding">
        <i class="material-icons">person_add</i> Create New User
      </label>
      <div class="fv-padding container">
        <fvForm class="fv-row">
          <fvFormElement class="fv-col-md-6" label="First Name">
            <fvInput v-model="exmps.firstName" placeholder="Enter First Name" />
          </fvFormElement>
          <fvFormElement class="fv-col-md-6" label="Last Name">
            <fvInput v-model="exmps.lastName" placeholder="Enter Last Name" />
          </fvFormElement>
          <fvFormElement class="fv-col-12" label="Gender" inline>
            <fvCheck v-model="exmps.gender" content="m">
              Men
            </fvCheck>
            <fvCheck v-model="exmps.gender" content="f">
              Women
            </fvCheck>
            <fvCheck v-model="exmps.gender" :content="null">
              Other
            </fvCheck>
          </fvFormElement>
          <fvFormElement class="fv-col-12" label="Home to Work Distance">
            <template slot="label" slot-scope="scope">
              {{ scope.label }}
              <span class="fv-margin-start-sm fv-text-primary">
                <span v-if="exmps.htw">~{{ exmps.htw }}km</span>
              </span>
            </template>
            <fvRange v-model="exmps.htw" :data="{ from: 1, to: 35 }" />
          </fvFormElement>
          <fvFormElement class="fv-col-sm-4" label="Is Maried?" inline>
            <fvSwitch
              v-model="exmps.married"
              @input="exmps.marriageDate = undefined"
            />
          </fvFormElement>
          <fvFormElement class="fv-col-sm-8" label="Date of Marriage">
            <fvDatepicker
              v-model="exmps.marriageDate"
              placeholder="Enter Date of Marriage"
              :disabled="!exmps.married"
            />
          </fvFormElement>
          <fvFormElement class="fv-col" label="Living Continent">
            <fvSelect
              v-model="exmps.continent"
              placeholder="Enter Living Continent"
              :options="[
                'Africa',
                'Antarctica',
                'Asia',
                'Europe',
                'North America',
                'Australia/Oceania',
                'South America'
              ]"
              text-key=""
              value-key=""
              disabled-key=""
            />
          </fvFormElement>
          <fvFormElement class="fv-col-12" label="Biography">
            <fvTextarea
              v-model="exmps.bio"
              placeholder="Enter Your Biography"
              auto-height
            />
          </fvFormElement>
        </fvForm>
      </div>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  data() {
    return {
      sidebar: false,
      docsMenu: false,
      slider: 'One',
      exmps: {
        htw: 13,
        firstName: undefined,
        lastName: undefined,
        gender: 'm',
        continent: undefined,
        married: undefined,
        marriageDate: undefined,
        bio: undefined
      }
    }
  },
  methods: {
    toggleSidebar() {
      this.sidebar = !this.sidebar
    },
    toggleDocsMenu() {
      setTimeout(() => {
        this.docsMenu = !this.docsMenu
      })
    }
  }
}
</script>

<style scoped>
.content {
  margin: 0 auto;
  max-width: 768px;
}
.sidebar {
  min-width: 300px;
}
</style>
