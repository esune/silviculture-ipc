<template>
  <div>
    <v-stepper v-model="step" alt-labels class="silv-stepper elevation-0" @change="setStep">
      <v-container v-if="!submissionComplete" fluid class="pa-0">
        <v-row class="header-row" no-gutters>
          <v-col cols="12" xl="10" offset-xl="1">
            <v-stepper-header class="elevation-0">
              <v-stepper-step
                :complete="step > 1"
                edit-icon="check"
                :editable="step > 1"
                step="1"
              >Before You Begin</v-stepper-step>

              <v-divider></v-divider>

              <v-stepper-step
                :complete="step > 2"
                edit-icon="check"
                :editable="step > 2"
                step="2"
              >Contact Information</v-stepper-step>

              <v-divider></v-divider>

              <v-stepper-step
                :complete="step > 3"
                edit-icon="check"
                :editable="step > 3"
                step="3"
              >Before Workers Arive</v-stepper-step>

              <v-divider></v-divider>

              <v-stepper-step
                :complete="step > 4"
                edit-icon="check"
                :editable="step > 4"
                step="4"
              >After Workers Arrive</v-stepper-step>

              <v-divider></v-divider>

              <v-stepper-step
                :complete="step > 5"
                edit-icon="check"
                :editable="step > 5"
                step="5"
              >If Workers Become Ill</v-stepper-step>

              <v-divider></v-divider>

              <v-stepper-step step="6">Review</v-stepper-step>
            </v-stepper-header>
          </v-col>
        </v-row>
      </v-container>

      <v-container>
        <v-row no-gutters>
          <v-col cols="12" xl="8" offset-xl="2">
            <v-stepper-items>
              <v-stepper-content step="1">
                <Step1 />
              </v-stepper-content>

              <v-stepper-content step="2">
                <Step2 />
              </v-stepper-content>

              <v-stepper-content step="3">
                <Step3 />
              </v-stepper-content>

              <v-stepper-content step="4">
                <Step4 />
              </v-stepper-content>

              <v-stepper-content step="5">
                <Step5 />
              </v-stepper-content>

              <v-stepper-content step="6">
                <Step6 />
              </v-stepper-content>
            </v-stepper-items>
          </v-col>
        </v-row>
      </v-container>
    </v-stepper>
  </div>
</template>

<script>
import { mapGetters, mapMutations } from 'vuex';

import Step1 from '@/components/form/Step1.vue';
import Step2 from '@/components/form/Step2.vue';
import Step3 from '@/components/form/Step3.vue';
import Step4 from '@/components/form/Step4.vue';
import Step5 from '@/components/form/Step5.vue';
import Step6 from '@/components/form/Step6.vue';

export default {
  name: 'Form',
  components: {
    Step1,
    Step2,
    Step3,
    Step4,
    Step5,
    Step6
  },
  data () {
    return {
    };
  },
  computed: {
    ...mapGetters('form', ['step', 'submissionComplete']),
  },
  methods: {
    ...mapMutations('form', ['setStep']),
  }
};
</script>
