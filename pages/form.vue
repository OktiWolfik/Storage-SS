<template>
  <v-sheet height="calc(100vh - 88px)" class="d-flex justify-center align-center">
    <v-sheet 
      elevation="4" 
      height="550px" 
      width="1000px" 
      color="" 
      class="rounded-lg pa-6"
    >
      <v-form>
        <v-container>
          <v-row>
            <v-col cols="3">
              <p>Опции</p>
              <v-radio-group>
                <v-radio
                  label="Поступление товара на склад"
                  value="1"
                />
                <v-radio
                  label="Возврат товара на склад"
                  value="2"
                />
                <v-radio
                  label="Отгрузка товара"
                  value="3"
                />
              </v-radio-group>
            </v-col>
            <v-col cols="4">
              <v-text-field
                label="Наименование"
                outlined
                clearable
              />
              <v-text-field
                label="Поставщик"
                outlined
                clearable
              />
            </v-col>
            <v-col cols="4">
              <v-text-field
                label="Количество"
                outlined
                clearable
              />
              <v-text-field
                label="Сумма"
                outlined
                clearable
              />
            </v-col> 
          </v-row>
          <v-row>
            <v-textarea
              outlined
              name="comment"
              label="Комментарий к документу"
              placeholder="Ваши пожелания"
            />
          </v-row>
          <v-row>
            <v-col cols="4">
              <v-menu
                ref="menu"
                v-model="menu"
                :close-on-content-click="false"
                :return-value.sync="date"
                transition="scale-transition"
                offset-y
                min-width="auto"
              >
                <template v-slot:activator="{ on, attrs }">
                  <v-text-field
                    v-model="date"
                    label="Дата составления"
                    prepend-icon="mdi-calendar"
                    v-bind="attrs"
                    v-on="on"
                  ></v-text-field>
                </template>
                <v-date-picker
                  v-model="date"
                  no-title
                  scrollable
                >
                  <v-spacer></v-spacer>
                  <v-btn
                    text
                    color="primary"
                    @click="menu = false"
                  >
                    Cancel
                  </v-btn>
                  <v-btn
                    text
                    color="primary"
                    @click="$refs.menu.save(date)"
                  >
                    OK
                  </v-btn>
                </v-date-picker>
              </v-menu>
            </v-col>
          </v-row>
          <div class="d-flex justify-end">
            <v-btn
              type="submit"
              color="primary"
              elevation="2"
              @click="clickHandler"
            >
              Отправить
            </v-btn>
          </div>
        </v-container>
      </v-form>
    </v-sheet>
  </v-sheet>
</template>

<script>
export default {
  name: 'FormPage',

  data() {
    return {
      date: (new Date(Date.now() - (new Date()).getTimezoneOffset() * 60000)).toISOString().substr(0, 10),
      menu: false,
    }
  },

  methods: {
    clickHandler() {
      console.log('clicked')
    }
  }
}
</script>
