<template>
  <div>
    <md-card>
      <md-card-media>
        <img :src="pec.img" alt="Ошибка" />
      </md-card-media>

      <md-card-header>
        <div class="md-title">{{ pec.name }}</div>
        <div class="md-subhead"></div>
      </md-card-header>

      <md-card-expand>
        <md-card-actions>
          <md-card-expand-trigger>
            <md-button class="md-raised md-primary"> Информация </md-button>
          </md-card-expand-trigger>
        </md-card-actions>
        <md-card-expand-content>
          <md-card-content>
           Ингридиенты: <span v-for="item in pec.ing" :key="item"> {{ item }}, </span>
          </md-card-content>
        </md-card-expand-content>
        <div class="probel"></div>
        <md-card-expand-content>
          <md-card-content>
            {{ pec.kyxna }}
          </md-card-content>
        </md-card-expand-content>
        <div class="probel"></div>
        <md-card-expand-content>
          <md-card-content>
          Время приготовления ~ {{ pec.time }}
          </md-card-content>
        </md-card-expand-content>
        <div class="probel"></div>
           <md-card-expand-content>
          <md-card-content>
          Способ приготовления: {{ pec.dis }}
          </md-card-content>
        </md-card-expand-content>
      </md-card-expand>
    </md-card>
  </div>
</template>

<script>
export default {
  name: "basa",
  props: {
    pec: {
      type: Object,
      default() {
        return {};
      },
    },
  },
};
</script>

<style scoped>
.md-card-actions {
  justify-content: center;
}
.card-expansion {
  height: 480px;
}

.md-card {
  width: 320px;
  margin: 4px;
  display: inline-block;
  vertical-align: top;
}
</style>