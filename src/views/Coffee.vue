<template>
  <v-container>
    <v-card>
      <v-form v-model="valid" @submit.prevent="save">
        <v-container>
          <v-row>
            <v-col cols="12" md="4">
              <v-text-field
                v-model="coffee.name"
                :rules="requiredRules"
                label="Name"
                required
              ></v-text-field>
            </v-col>
            <v-col cols="12" md="4">
              <v-text-field
                v-model="coffee.shop_name"
                :rules="requiredRules"
                label="Shop Name"
                required
              ></v-text-field>
            </v-col>
            <v-col cols="12" md="4">
              <v-text-field
                v-model="coffee.shop_link"
                :rules="requiredRules"
                label="Shop Link"
                required
              ></v-text-field>
            </v-col>
            <v-col cols="12" md="4">
              <v-text-field
                v-model="coffee.roast"
                :rules="requiredRules"
                label="Roast Level"
                required
              ></v-text-field>
            </v-col>
            <v-col cols="12" md="4">
              <v-text-field
                v-model="coffee.testing_note"
                :rules="requiredRules"
                label="Testing Note"
                required
              ></v-text-field>
            </v-col>
            <v-col cols="12" md="4">
              <v-select
                v-model="coffee.process"
                :rules="requiredRules"
                :items="process"
                label="Standard"
              ></v-select>
            </v-col>
            <v-col cols="12" md="4">
              <v-text-field
                v-model="coffee.price"
                :rules="requiredRules"
                label="Price"
                required
              ></v-text-field>
            </v-col>
            <v-col cols="12" md="4">
              <v-text-field
                v-model="coffee.weight"
                :rules="requiredRules"
                label="Weight"
                required
              ></v-text-field>
            </v-col>
            <v-col cols="12" md="4">
              <v-text-field
                v-model="coffee.rating"
                :rules="requiredRules"
                label="Rating"
                required
              ></v-text-field>
            </v-col>
            <v-col cols="12" md="4">
              <v-text-field
                v-model="coffee.images.portrait"
                :rules="requiredRules"
                label="Image Portrait"
                required
              ></v-text-field>
            </v-col>
            <v-col cols="12" md="4">
              <v-text-field
                v-model="coffee.images.landscape"
                :rules="requiredRules"
                label="Image Landscape"
                required
              ></v-text-field>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <v-btn
                :disabled="!valid"
                type="submit"
                color="primary"
                class="mx-1"
                >Submit</v-btn
              >
              <v-btn color="error" class="mx-1">Clear</v-btn>
            </v-col>
          </v-row>
        </v-container>
      </v-form>
    </v-card>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      valid: false,
      requiredRules: [
        (v) => !!v || "Required",
        (v) => v.length <= 50 || "จำกัดไม่เกิน 50 ตัวอักษร",
      ],
      process: ["Wash Process", "Honey Process", "Natural Process"],
      coffee: {
        name: "",
        shop_name: "",
        shop_link: "",
        price: "",
        rating: "",
        process: "",
        testing_note: "",
        roast: "",
        weight: "",
        images: {
          portrait: "",
          landscape: "",
        },
      },
    };
  },
  methods: {
    save() {
      alert("save");
      console.log(`Coffee Object =>`, this.coffee);
    },
  },
};
</script>
