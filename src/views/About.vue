<template>
  <div>
    <div class="md-layout md-gutter md-alignment-center-center">
      <div class="md-layout-item md-size-60">
        <md-field>
          <md-select
            v-model="kyxna"
            name="kyxna"
            id="kyxna"
            placeholder="Кухня"
          >
            <md-option
              v-for="(item, index) in allKyxna"
              :key="index"
              :value="item"
              >{{ item }}
            </md-option>
          </md-select>
        </md-field>
      </div>
    </div>
    <div class="sbros">
      <md-button class="md-raised md-primary" v-on:click="clear"
        >Сброс
      </md-button>
    </div>
    <div class="about">
      <basa
        v-for="(pec, index) in filtered"
        :key="index"
        :pec="pec"
        :index="index"
      >
      </basa>
    </div>
  </div>
</template>

<script>
import basa from "../components/basa";
import pecept from "../recepti/pecept";
export default {
  name: "about",
  components: { basa },
  data: () => ({
    pecept: pecept,
    filtered: {},
    kyxna: null,
    allKyxna: [],
  }),
  methods: {
    clear: function () {
      console.log("kryak");
      this.kyxna = null;
    },
  },
  // computed: {
  //   getKyxna: function () {
  //     for (let key in pecept) {
  //       this.allKyxna.push(pecept[key].kyxna)
  //     }
  //     console.log(this.allKyxna)
  //   return this.allKyxna
  //   },
  // },
  watch: {
    kyxna: function () {
      if (this.kyxna == null) {
        this.filtered = this.pecept;
      } else {
        this.filtered = {};
        for (let key in pecept) {
          if (pecept[key].kyxna == this.kyxna) {
            this.filtered[key] = pecept[key];
            console.log(this.filtered[key].kyxna);
          }
        }
      }
    },
  },
  mounted: function () {
    this.filtered = this.pecept;
    for (let key in pecept) {
      this.allKyxna.push(pecept[key].kyxna);
    }
    this.allKyxna = Array.from(new Set(this.allKyxna));
    console.log(this.allKyxna);
  },
};
</script>

<style>
.about {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>