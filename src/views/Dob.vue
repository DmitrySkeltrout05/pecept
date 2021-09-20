<template>
  <div class="md-layout md-gutter md-alignment-center-center">
    <div class="md-layout-item md-size-40 md-small-size-100">
      <md-card>
        <md-card-header>
          <div class="md-title">Карта регистрации блюда</div>
        </md-card-header>

        <md-card-content>
          Заполнив эту карточку и отправив,<br />
          вы сможете разместить на сайте своё блюдо<br />
          Связь с разроботичком: Moia-pochta@mail.ru
        </md-card-content>
        <div class="md-layout md-gutter md-alignment-center-center">
          <div class="md-layout-item md-size-90">
            <md-field>
              <label>Имя и фамилия</label>
              <md-input v-model="form.nameFamily"></md-input>
            </md-field>
            <md-field>
              <label>Название блюда</label>
              <md-input v-model="form.dishName"></md-input>
            </md-field>
            <md-field>
              <label>К какой национальности принадлежит?</label>
              <md-input v-model="form.dishNational"></md-input>
            </md-field>
            <md-field>
              <label>Фотография</label>
              <md-file v-model="form.dishPhoto" />
            </md-field>
            <md-field>
              <label>Продукты</label>
              <md-input v-model="form.products"></md-input>
              <span class="md-helper-text">По форме: Говядина (350 грамм)</span>
            </md-field>
            <md-field>
              <label>Способ приготовления</label>
              <md-textarea v-model="form.recipe" md-autogrow></md-textarea>
            </md-field>
            <md-field>
              <label>Время приготовления</label>
              <md-input v-model="form.time"></md-input>
              <span class="md-helper-text">В часах</span>
            </md-field>
            <md-field>
              <label>Как с вами связаться?</label>
              <md-input v-model="form.mail"></md-input>
              <span class="md-helper-text">Почта @mail.ru</span>
            </md-field>
          </div>
        </div>
        <md-card-actions>
          <md-button v-on:click="clearForm">Отправить</md-button>
        </md-card-actions>
      </md-card>
    </div>
  </div>
</template>

<script>
export default {
  data: function(){
    return{
      form: {
        nameFamily: null,
        dishName: null,
        dishNational: null,
        dishPhoto: null,
        products: null,
        recipe: null,
        time: null,
        mail: null,
      }
    }
  },
  methods: {
    send: function(){
      console.log(this.form)
    },
    clearForm: function(){
      this.form.nameFamily = null
      this.form.dishName = null
      this.form.dishNational = null
      this.form.dishPhoto = null
      this.form.products = null
      this.form.recipe = null
      this.form.time = null
      this.form.mail = null
    }
  }
};
</script>

<style >
</style>
