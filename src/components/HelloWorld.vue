<template>
  <v-container class="fill-height">
    <v-responsive class="align-center text-center fill-height">
      <v-img height="300" src="@/assets/logo.svg" />

      <div class="text-body-2 font-weight-light mb-n1">Welcome to</div>

      <h1 class="text-h2 font-weight-bold">Vuetify Demo</h1>
      <v-divider class="my-5"></v-divider>
      <v-row>
        <!-- Input -->
        <v-col>
          <h1>Input</h1>
          <v-table density="comfortable">
            <thead>
              <tr>
                <th class="text-center text-white">
                  Title
                </th>
                <th class="text-center text-white">
                  Preview
                </th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td class="text-center">Normal</td>
                <td>
                  <v-text-field
                    label="標題"
                    placeholder="請輸入關鍵字"
                    variant="outlined"
                    density="compact"
                    class="w-300 d-inline-block"
                    color="blue-darken-1"
                    clearable
                    persistent-placeholder
                    hide-details
                  ></v-text-field>
                </td>
              </tr>
              <tr>
                <td class="text-center">Limit</td>
                <td>
                  <v-text-field
                    label="標題"
                    placeholder="請輸入關鍵字"
                    variant="outlined"
                    density="compact"
                    class="w-300 d-inline-block mt-5"
                    color="blue-darken-1"
                    maxlength="20"
                    clearable
                    counter
                    persistent-placeholder
                    persistent-counter
                  ></v-text-field>
                </td>
              </tr>
              <tr>
                <td class="text-center">Disabled</td>
                <td>
                  <v-text-field
                    label="標題"
                    placeholder="請輸入關鍵字"
                    variant="outlined"
                    density="compact"
                    class="w-300 d-inline-block"
                    color="blue-darken-1"
                    persistent-placeholder
                    hide-details
                    disabled
                    v-model="disabledInputValue"
                  ></v-text-field>
                </td>
              </tr>
              <tr>
                <td class="text-center">Error</td>
                <td>
                  <v-text-field
                    label="必填欄位"
                    placeholder="請輸入關鍵字"
                    variant="outlined"
                    density="compact"
                    class="w-300 d-inline-block text-left"
                    color="blue-darken-1"
                    :error-messages="'請輸入關鍵字'"
                    :rules="[rules.required]"
                    persistent-placeholder
                    persistent-hint
                    v-model="requiredInputValue"
                  ></v-text-field>
                </td>
              </tr>
            </tbody>
          </v-table>
        </v-col>
        <!-- textarea -->
        <v-col>
          <h1>Textarea</h1>
          <v-table density="comfortable">
            <thead>
              <tr class="bg-blue-darken-3">
                <th class="text-center text-white">
                  Title
                </th>
                <th class="text-center text-white">
                  Preview
                </th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td class="text-center">Normal</td>
                <td>
                  <v-textarea
                    label="標題"
                    variant="outlined"
                    rows="4"
                    row-height="15"
                    placeholder="請輸入內文"
                    persistent-placeholder
                    hide-details
                  ></v-textarea>
                </td>
              </tr>
              <tr>
                <td class="text-center">Limit</td>
                <td>
                  <v-textarea
                    label="計算字數"
                    variant="outlined"
                    rows="4"
                    row-height="15"
                    placeholder="請輸入內文"
                    maxlength="200"
                    counter
                    persistent-counter
                    persistent-placeholder
                  ></v-textarea>
                </td>
              </tr>
              <tr>
                <td class="text-center">Disabled</td>
                <td>
                  <v-textarea
                    label="標題"
                    variant="outlined"
                    rows="4"
                    row-height="15"
                    placeholder="請輸入內文"
                    v-model="disabledTextareaValue"
                    disabled
                    persistent-placeholder
                    hide-details
                  ></v-textarea>
                </td>
              </tr>
            </tbody>
          </v-table>
        </v-col>
        <!-- datePicker -->
         <v-col>
          <h1>DatePicker</h1>
          <v-table density="comfortable">
            <thead>
              <tr>
                <th class="text-center text-white">Title</th>
                <th class="text-center text-white">Preview</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td class="text-center">Single</td>
                <td>
                  <date-single-picker></date-single-picker>
                </td>
              </tr>
              <tr>
                <td class="text-center">Multiple</td>
                <td>
                  <date-multiple-picker></date-multiple-picker>
                </td>
              </tr>
            </tbody>
          </v-table>
        </v-col>
        <!-- Button -->
        <v-col cols="12" col="12">
          <h1>Button</h1>
          <v-table density="comfortable">
            <thead>
              <tr>
                <th class="text-center text-white">
                  Type
                </th>
                <th class="text-center text-white">
                  Default
                </th>
                <th class="text-center text-white">
                  Disabled
                </th>
                <th class="text-center text-white">
                  Icon(Left)
                </th>
                <th class="text-center text-white">
                  Icon(Right)
                </th>
              </tr>
            </thead>
            <tbody>
              <!-- Primary -->
              <tr>
                <td class="text-center">Primary</td>
                <td>
                  <v-btn
                    variant="elevated"
                    color="indigo-darken-3"
                  >Button</v-btn>
                </td>
                <td>
                  <v-btn
                    variant="elevated"
                    color="indigo-darken-3"
                    disabled
                  >Button</v-btn>
                </td>
                <td>
                  <v-btn
                    variant="elevated"
                    color="indigo-darken-3"
                    prepend-icon="$vuetify"
                  >Button</v-btn>
                </td>
                <td>
                  <v-btn
                    variant="elevated"
                    color="indigo-darken-3"
                    append-icon="$vuetify"
                  >Button</v-btn>
                </td>
              </tr>
              <!-- Secondary -->
              <tr>
                <td class="text-center">Secondary</td>
                <td>
                  <v-btn
                    variant="tonal"
                    color="indigo-darken-3"
                  >Button</v-btn>
                </td>
                <td>
                  <v-btn
                    variant="tonal"
                    color="indigo-darken-3"
                    disabled
                  >Button</v-btn>
                </td>
                <td>
                  <v-btn
                    variant="tonal"
                    color="indigo-darken-3"
                    prepend-icon="$vuetify"
                  >Button</v-btn>
                </td>
                <td>
                  <v-btn
                    variant="tonal"
                    color="indigo-darken-3"
                    append-icon="$vuetify"
                  >Button</v-btn>
                </td>
              </tr>
              <!-- Link -->
              <tr>
                <td class="text-center">Link</td>
                <td>
                  <v-btn
                    variant="text"
                    color="indigo-darken-3"
                  >Button</v-btn>
                </td>
                <td>
                  <v-btn
                    variant="text"
                    color="indigo-darken-3"
                    disabled
                  >Button</v-btn>
                </td>
                <td>
                  <v-btn
                    variant="text"
                    color="indigo-darken-3"
                    prepend-icon="$vuetify"
                  >Button</v-btn>
                </td>
                <td>
                  <v-btn
                    variant="text"
                    color="indigo-darken-3"
                    append-icon="$vuetify"
                  >Button</v-btn>
                </td>
              </tr>
               <!-- Outline -->
               <tr>
                <td class="text-center">Osutlined</td>
                <td>
                  <v-btn
                    variant="outlined"
                    color="indigo-darken-3"
                  >Button</v-btn>
                </td>
                <td>
                  <v-btn
                    variant="outlined"
                    color="indigo-darken-3"
                    disabled
                  >Button</v-btn>
                </td>
                <td>
                  <v-btn
                    variant="outlined"
                    color="indigo-darken-3"
                    prepend-icon="$vuetify"
                  >Button</v-btn>
                </td>
                <td>
                  <v-btn
                    variant="outlined"
                    color="indigo-darken-3"
                    append-icon="$vuetify"
                  >Button</v-btn>
                </td>
              </tr>
            </tbody>
          </v-table>
        </v-col>
      </v-row>

    </v-responsive>
  </v-container>
</template>

<script setup>
  import {ref, reactive} from 'vue'
  import dateSinglePicker from './dateSinglePicker.vue';
  import dateMultiplePicker from './dateMultiplePicker.vue';
  
  
  const disabledInputValue = ref('禁用文字');
  const requiredInputValue = ref('');
  
  const disabledTextareaValue = ref('禁用內文');

  const rules = reactive({
    required: value => !!value || '此為必填欄位.',
  });

  const date = reactive('2023-07-18');

</script>


<style lang="scss">
  th{
    background:#1565C0;
  }

  td{
    padding:15px !important;
    height:90px !important;
  }

  .w-300{
    width:300px;
  }

 </style>