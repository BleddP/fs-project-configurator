<template>
  <div class="flex-wrapper padding">
    <div class="container-center">
      <!-- Which Door Type? -->
      <div class="question-card">
        <span class="question-number">Vraag 1</span>
        <h3>Welk Deurtype?</h3>
        <input type="radio" name="door-type" id="doortype-a" class="radio" value="a" />
        <label class="radio-label" for="doortype-a">Deurtype A</label>
        <br />
        <input type="radio" name="door-type" id="doortype-b" class="radio" value="b" />
        <label class="radio-label" for="doortype-b">Deurtype B</label>
      </div>

      <!-- Door width? -->
      <div class="question-card">
        <span class="question-number">Vraag 2</span>
        <h3>Wat is de breedte van de roldeur?</h3>
        <span class="question-comment">Eenheid in centimeters</span>
        <br />
        <input class="textfield" type="text" />
      </div>

      <!-- Door height? -->
      <div class="question-card">
        <span class="question-number">Vraag 2</span>
        <h3>Wat is de hoogte van de roldeur?</h3>
        <span class="question-comment">Eenheid in centimeters</span>
        <br />
        <input class="textfield" type="text" />
      </div>

      <!-- Door assembly side Left / Right  -->
      <div class="question-card">
        <span class="question-number">Vraag 4</span>
        <h3>Aan welke zijde dient de roldeur gemonteerd te worden?</h3>
        <input type="radio" name="door-side" id="left" class="radio" value="left" />
        <label class="radio-label" for="left">Links</label>
        <br />
        <input type="radio" name="door-side" id="right" class="radio" value="right" />
        <label class="radio-label" for="right">Rechts</label>
      </div>

      <!-- Self-Healing? -->
      <div class="question-card">
        <span class="question-number">Vraag 5</span>
        <h3>Is de deur zelfherstellend?</h3>
        <input type="radio" name="self-healing" id="self-healing-yes" class="radio" value="true" />
        <label class="radio-label" for="self-healing-yes">Ja</label>
        <br />
        <input type="radio" name="self-healing" id="self-healing-no" class="radio" value="false" />
        <label class="radio-label" for="self-healing-no">Nee</label>
      </div>

      <!-- Stainless Steel? -->
      <div class="question-card">
        <span class="question-number">Vraag 6</span>
        <h3>Is RVS van toepassing</h3>
        <input type="radio" name="stainless-steel" id="stainless-yes" class="radio" value="true" />
        <label class="radio-label" for="stainless-yes">Ja</label>
        <br />
        <input type="radio" name="stainless-steel" id="stainless-no" class="radio" value="false" />
        <label class="radio-label" for="stainless-no">Nee</label>
      </div>

      <!-- Wind Load? -->
      <div class="question-card">
        <span class="question-number">Vraag 7</span>
        <h3>Windbelasting</h3>
        <div class="row">
          <div class="col-1">
            <input type="radio" name="wind-load" id="windload-1" class="radio" value="1" />
            <label class="radio-label" for="windload-1">Optie 1</label>
          </div>
          <div class="col-1">
            <input type="radio" name="wind-load" id="windload-2" class="radio" value="2" />
            <label class="radio-label" for="windload-2">Optie 2</label>
          </div>
          <div class="col-1">
            <input type="radio" name="wind-load" id="windload-3" class="radio" value="3" />
            <label class="radio-label" for="windload-3">Optie 3</label>
          </div>
          <div class="col-1">
            <input type="radio" name="wind-load" id="windload-4" class="radio" value="4" />
            <label class="radio-label" for="windload-4">Optie 4</label>
          </div>
          <div class="col-1">
            <input type="radio" name="wind-load" id="windload-5" class="radio" value="5" />
            <label class="radio-label" for="windload-5">Optie 5</label>
          </div>
          <div class="col-1">
            <input type="radio" name="wind-load" id="windload-6" class="radio" value="6" />
            <label class="radio-label" for="windload-6">Optie 6</label>
          </div>
          <div class="col-1">
            <input type="radio" name="wind-load" id="windload-7" class="radio" value="7" />
            <label class="radio-label" for="windload-7">Optie 7</label>
          </div>
          <div class="col-1">
            <input type="radio" name="wind-load" id="windload-8" class="radio" value="8" />
            <label class="radio-label" for="windload-8">Optie 8</label>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ConfigQuestions"
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
  font-family: "Rubik", sans-serif;
}

.question-comment {
  text-transform: uppercase;
  font-weight: bold;
}
</style>
