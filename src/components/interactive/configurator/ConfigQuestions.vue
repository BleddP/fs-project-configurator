<template>
  <div class="flex-wrapper padding">
    <div class="container-center">
      <!-- Which Door Type? -->
      <div class="question-card">
        <span class="question-number">Vraag 1</span>
        <h3>Welk Deurtype?</h3>
        <input
          type="radio"
          name="door-type"
          id="doortype-a"
          class="radio"
          value="A"
          @click="selectDoorType('A')"
        />
        <label class="radio-label" for="doortype-a">Deurtype A</label>
        <br />
        <input
          type="radio"
          name="door-type"
          id="doortype-b"
          class="radio"
          value="B"
          @click="selectDoorType('B')"
        />
        <label class="radio-label" for="doortype-b">Deurtype B</label>
      </div>

      <!-- Door width? -->
      <div class="question-card">
        <form>
          <span class="question-number">Vraag 2</span>
          <h3>Wat is de breedte van de roldeur?</h3>
          <span class="question-comment">Eenheid in centimeters</span>
          <br />
          <input
            class="textfield"
            type="text"
            @input="setWidth($event.target.value)"
          />
        </form>
      </div>

      <!-- Door height? -->
      <div class="question-card">
        <span class="question-number">Vraag 2</span>
        <h3>Wat is de hoogte van de roldeur?</h3>
        <span class="question-comment">Eenheid in centimeters</span>
        <br />
        <input
          class="textfield"
          type="text"
          @input="setHeight($event.target.value)"
        />
      </div>

      <!-- Door assembly side Left / Right  -->
      <div class="question-card">
        <span class="question-number">Vraag 4</span>
        <h3>Aan welke zijde dient de roldeur gemonteerd te worden?</h3>
        <input
          type="radio"
          name="door-side"
          id="left"
          class="radio"
          value="left"
          @click="selectAssembly('left')"
        />
        <label class="radio-label" for="left">Links</label>
        <br />
        <input
          type="radio"
          name="door-side"
          id="right"
          class="radio"
          value="right"
          @click="selectAssembly('right')"
        />
        <label class="radio-label" for="right">Rechts</label>
      </div>

      <!-- Self-Healing? -->
      <div class="question-card">
        <span class="question-number">Vraag 5</span>
        <h3>Is de deur zelfherstellend?</h3>
        <input
          type="radio"
          name="self-healing"
          id="self-healing-yes"
          class="radio"
          value="true"
          @click="selectSelfHealing(true)"
        />
        <label class="radio-label" for="self-healing-yes">Ja</label>
        <br />
        <input
          type="radio"
          name="self-healing"
          id="self-healing-no"
          class="radio"
          value="false"
          @click="selectSelfHealing(false)"
        />
        <label class="radio-label" for="self-healing-no">Nee</label>
      </div>

      <!-- Stainless Steel? -->
      <div class="question-card">
        <span class="question-number">Vraag 6</span>
        <h3>Is RVS van toepassing</h3>
        <input
          type="radio"
          name="stainless-steel"
          id="stainless-yes"
          class="radio"
          value="true"
          @click="selectStainlessSteel(true)"
        />
        <label class="radio-label" for="stainless-yes">Ja</label>
        <br />
        <input
          type="radio"
          name="stainless-steel"
          id="stainless-no"
          class="radio"
          value="false"
          @click="selectStainlessSteel(false)"
        />
        <label class="radio-label" for="stainless-no">Nee</label>
      </div>

      <!-- Wind Load? Use a v-for to generate a list of 8 indexes -->
      <div class="question-card">
        <span class="question-number">Vraag 7</span>
        <h3>Windbelasting</h3>
        <div class="row">
          <div v-for="index in 8" :key="index">
            <div class="col-1">
              <input
                type="radio"
                name="wind-load"
                v-bind:id="index"
                class="radio"
                value="index"
                @click="selectWindLoad(index)"
              />
              <label class="radio-label" v-bind:for="'windload-' + index"
                >Optie {{ index }}</label
              >
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ConfigQuestions',
  props: {
    selectDoorType: Function,
    selectAssembly: Function,
    selectSelfHealing: Function,
    selectStainlessSteel: Function,
    selectWindLoad: Function,
  },
  methods: {
    setWidth(value) {
      this.$emit('select-width', value);
    },
    setHeight(value) {
      this.$emit('select-height', value);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.question-card {
  margin-top: 25px;
  margin-bottom: 25px;
  background-color: white;
  min-height: 200px;
  padding: 50px;
}

.question-number {
  color: orange;
  font-weight: bold;
}

label {
  font-family: 'Rubik', sans-serif;
}

.question-comment {
  text-transform: uppercase;
  font-weight: bold;
}
</style>
