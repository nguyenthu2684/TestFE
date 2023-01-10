<template>
  <div>
    <b-container class="row-change-imf-user">
      <b-row>
        <b-col cols="2">
          <b-form-select
            v-model="select"
            :options="nation"
            style="width: 100px; margin-bottom: 100px"
          ></b-form-select
        ></b-col>
        <b-col
          ><b-input-group>
            <b-form-input
              v-model="inputChange"
              :formatter="formatter"
              v-on:keypress="NumbersOnly"
            ></b-form-input> </b-input-group
        ></b-col>
      </b-row>

      <!-- <b-form-select
        v-model="selected"
        :options="nation"
        size="sm"
        class="mt-3"
      ></b-form-select> -->

      <div class="mt-3">
        Selected: <strong>{{ select }}</strong>
        <br />
        Selected input: <strong>{{ inputChange }}</strong>
        <br />
        <!-- Change: <strong>{{ change }}</strong> -->
      </div>
    </b-container>
  </div>
</template>

<script>
export default {
  mame: "test-value-input ",
  data() {
    return {
      inputChange: null,

      select: "VN",
      nation: [
        { value: "VN", text: "VN" },
        { value: "ENG", text: "ENG" },
      ],
    };
  },
  created() {},
  watch: {},
  methods: {
    formatter(value) {
      let number = 0;

      // if (!value.indexOf(",") !== -1) {
      //   number = Number(value.replace(/\./g, ""));
      //   console.log(number);
      //   return number.toLocaleString("vi-VN", {
      //     maximumFractionDigits: 2,
      //   });
      // } else {
      //   number = Number(value.replace(/\./g, ""));
      // }
      // return number;

      // if (value.indexOf(",") !== -1) {
      //   console.log("val", value.indexOf(","));
      //   num2 = Number(value.replace(/\,/g, "."));
      //   console.log(value);
      //   console.log("??", num2);
      //   console.log("???", value.replace(/\,/g, "."));
      //   return num2.toLocaleString("vi-VN", {
      //     maximumFractionDigits: 2,
      //   });
      // } else {
      //   number = Number(value.replace(/\./g, ""));
      //   console.log(number);
      //   return number.toLocaleString("vi-VN", {
      //     maximumFractionDigits: 2,
      //   });
      // }

      number = Number(value.replace(/\,/g, ""));
      console.log(number);
      return number.toLocaleString("es-US", {
        maximumFractionDigits: 2,
      });
      // }?

      // number = Number(value.replace(",", "."));
    },

    NumbersOnly(evt) {
      evt = evt ? evt : window.event;
      var charCode = evt.which ? evt.which : evt.keyCode;
      if (
        charCode > 31 &&
        (charCode < 48 || charCode > 57) &&
        charCode != 46 &&
        charCode != 44
      ) {
        evt.preventDefault();
      } else {
        return true;
      }
    },
  },
  //  (charCode > 48 && charCode < 57) || charCode == 44 || charCode == 46
  //  charCode > 31 && (charCode < 48 || charCode > 57) &&  charCode !== 46
  computed: {
    // formatInput() {
    //   if (this.select == "VN") {
    //     let temp = Number(this.inputChange);
    //     this.chanege = temp.toLocaleString("vi-VN");
    //     this.inputChange = this.chanege;
    //   } else if (this.select == "ENG") {
    //     let text = this.inputChange.toLocaleString("es-US", {
    //       style: "currency",
    //       currency: "USD",
    //     });
    //     this.chanege = text;
    //   }
    // },
  },
};
</script>

<style lang="scss" scoped></style>
