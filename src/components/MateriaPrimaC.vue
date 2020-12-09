<template>
  <v-container>
    <v-row align="center">
      <v-col class="d-flex" cols="12" sm="12" md="12" fluid>
        <v-card elevation="24" outlined max-width="10000">
          <v-container fluid>
            <v-row align="center">
              <v-col class="d-flex" cols="12" sm="2">
                <v-select :items="items" label="Estado" dense></v-select>
              </v-col>

              <v-col class="d-flex" cols="12" sm="2">
                <v-select :items="items" label="Fecha inicial" dense></v-select>
              </v-col>
              <v-col class="d-flex" cols="12" sm="2">
                <v-select :items="items" label="Fecha final" dense></v-select>
              </v-col>
              <v-col class="d-flex" cols="12" sm="6" md="6">
                <v-text-field
                  placeholder="...Search"
                  prepend-inner-icon="mdi-magnify"
                  clearable
                ></v-text-field>
              </v-col>
            </v-row>
          </v-container>
        </v-card>
      </v-col>
    </v-row>
    <v-row align="center">
      <v-col >
      <v-card fluid elevation="24" max-width="8500" max-height="4000">
        
        <v-row align="center">
          <v-col class="d-flex" cols="12" sm="6" md="3">
            <v-card elevation="24">
              <v-card-title><h3>Materia Prima</h3></v-card-title>
              <v-card-text>Codigo</v-card-text>
              <v-spacer />
              <v-card-text>Cantidad</v-card-text>
              <v-card-actions>
                <v-btn>
                  <v-icon>mdi-account-multiple-outline</v-icon>
                </v-btn>
                 <v-btn>
                  <v-icon>mdi-account-multiple-outline</v-icon>
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
         <v-col class="d-flex" cols="12" sm="6" md="3">
            <v-card elevation="24">
              <v-card-title><h3>Materia Prima</h3></v-card-title>
              <v-card-text>Codigo</v-card-text>
              <v-spacer />
              <v-card-text>Cantidad</v-card-text>
              <v-card-actions>
                <v-btn>
                  <v-icon>mdi-account-multiple-outline</v-icon>
                </v-btn>
                 <v-btn>
                  <v-icon>mdi-account-multiple-outline</v-icon>
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
          <v-col class="d-flex" cols="12" sm="6" md="3">
            <v-card elevation="24">
              <v-card-title><h3>Materia Prima</h3></v-card-title>
              <v-card-text>Codigo</v-card-text>
              <v-spacer />
              <v-card-text>Cantidad</v-card-text>
               <v-card-actions>
                <v-btn>
                  <v-icon>mdi-account-multiple-outline</v-icon>
                </v-btn>
                 <v-btn>
                  <v-icon>mdi-account-multiple-outline</v-icon>
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
         <v-col class="d-flex" cols="12" sm="6" md="3">
            <v-card elevation="10">
              <v-card-title><h3>Materia Prima</h3></v-card-title>
              <v-card-text>Codigo</v-card-text>
              <v-spacer />
              <v-card-text>Cantidad</v-card-text>
              <v-card-actions>
                <v-btn>
                  <v-icon>mdi-account-multiple-outline</v-icon>
                </v-btn>
                 <v-btn>
                  <v-icon>mdi-account-multiple-outline</v-icon>
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>

        <v-row align="center">
          <v-col class="d-flex" cols="12" sm="6" md="3">
            <v-card elevation="24">
              <v-card-title><h3>Materia Prima</h3></v-card-title>
              <v-card-text>Codigo</v-card-text>
              <v-spacer />
              <v-card-text>Cantidad</v-card-text>
              <v-card-actions>
                <v-btn>
                  <v-icon>mdi-account-multiple-outline</v-icon>
                </v-btn>
                 <v-btn>
                  <v-icon>mdi-account-multiple-outline</v-icon>
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
         <v-col class="d-flex" cols="12" sm="6" md="3">
            <v-card elevation="24">
              <v-card-title><h3>Materia Prima</h3></v-card-title>
              <v-card-text>Codigo</v-card-text>
              <v-spacer />
              <v-card-text>Cantidad</v-card-text>
              <v-card-actions>
                <v-btn>
                  <v-icon>mdi-account-multiple-outline</v-icon>
                </v-btn>
                 <v-btn>
                  <v-icon>mdi-account-multiple-outline</v-icon>
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
          <v-col class="d-flex" cols="12" sm="6" md="3">
            <v-card elevation="24">
              <v-card-title><h3>Materia Prima</h3></v-card-title>
              <v-card-text>Codigo</v-card-text>
              <v-spacer />
              <v-card-text>Cantidad</v-card-text>
               <v-card-actions>
                <v-btn>
                  <v-icon>mdi-account-multiple-outline</v-icon>
                </v-btn>
                 <v-btn>
                  <v-icon>mdi-account-multiple-outline</v-icon>
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
         <v-col class="d-flex" cols="12" sm="6" md="3">
            <v-card elevation="10">
              <v-card-title><h3>Materia Prima</h3></v-card-title>
              <v-card-text>Codigo</v-card-text>
              <v-spacer />
              <v-card-text>Cantidad</v-card-text>
              <v-card-actions>
                <v-btn>
                  <v-icon>mdi-account-multiple-outline</v-icon>
                </v-btn>
                 <v-btn>
                  <v-icon>mdi-account-multiple-outline</v-icon>
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>
      </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>


<script>
export default {
  data: () => ({
    items: ["Foo", "Bar", "Fizz", "Buzz"],
  }),
};
</script>