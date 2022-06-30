<template>
  <div class="hesap">
    <h1>Proje Ücreti</h1>
    <form @submit.prevent="lastPrice">
      <div class="form-group">
        <label for="yapıA">Yapı Alanı</label>
        <input
          autocomplete="off"
          v-model="hesap.yapıA"
          type="text"
          class="form-control data"
          id="yapıA"
        />
      </div>
      <div class="form-group">
        <label for="bolgeK">Bölge Katsayısı</label>
        <input
          autocomplete="off"
          v-model="hesap.bolgeK"
          type="text"
          class="form-control data"
          id="bolgeK"
        />
      </div>
      <div class="form-group">
        <label for="birimM">Birim Maliyeti</label>
        <input
          autocomplete="off"
          v-model="hesap.birimM"
          type="text"
          class="form-control data"
          id="birimM"
        />
      </div>
      <div class="form-group">
        <label for="yapıSK">BYapı Sınıf Katsayısı</label>
        <input
          autocomplete="off"
          v-model="hesap.yapıSK"
          type="text"
          class="form-control data"
          id="yapıSK"
        />
      </div>
      <div class="form-group">
        <label for="projeUO">Proje Ü.O.</label>
        <input
          autocomplete="off"
          v-model="hesap.projeUO"
          type="text"
          class="form-control data"
          id="projeUO"
        />
      </div>
      <div class="form-group">
        <label for="hizmetB">Hizmet B</label>
        <select
          v-model="hesap.hizmetB"
          type="text"
          class="form-control data"
          id="hizmetB"
        >
          <option selected></option>
          <option value="255">1. Sınıf A</option>
          <option value="390">1. Sınıf B</option>
          <option value="640">2. Sınıf A</option>
          <option value="940">2. Sınıf B</option>
          <option value="1030">2. Sınıf C</option>
          <option value="1360">3. Sınıf A</option>
          <option value="1800">3. Sınıf B</option>
          <option value="1920">4. Sınıf A</option>
          <option value="2300">4. Sınıf B</option>
          <option value="2480">4. Sınıf C</option>
          <option value="2970">5. Sınıf A</option>
          <option value="3600">5. Sınıf B</option>
          <option value="4000">5. Sınıf C</option>
          <option value="4700">5. Sınıf D</option>
        </select>
      </div>
      <div class="form-group">
        <label for="projeYK">Proje YK.</label>
        <select v-model="hesap.projeYK" class="form-control data" id="projeYK">
          <option selected></option>
          <option value="1">
            Kâgir-Yüzeysel & Kâgir-Derin & Betonarme-Yüzeysel
          </option>
          <option value="1.1">Betonarme-Derin & Çelik-Yüzeysel</option>
          <option value="1.2">Çelik-Derin</option>
        </select>
      </div>
      <button type="submit" class="btn btn-sm btn-success">Ekle</button>
    </form>
  </div>
</template>
<script>
export default {
  name: "calc-place",
  data() {
    return {
      hesap: {
        yapıA: "",
        bolgeK: "",
        birimM: "",
        yapıSK: "",
        projeUO: "",
        projeYK: "",
        hizmetB: "",
      },
    };
  },
  methods: {
    lastPrice() {
      var son =
        parseFloat(this.hesap.bolgeK)*
        parseFloat(this.hesap.yapıA)*
        parseFloat(this.hesap.birimM)*
        parseFloat(this.hesap.yapıSK)*
        parseFloat(this.hesap.projeUO)*
        parseFloat(this.hesap.projeYK)*
        parseFloat(this.hesap.hizmetB)*0.75
        ;
      alert("fiyat=" + son);
    },
  },
};
</script>
<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Merriweather:wght@700&display=swap%27");

.hesap {
  background-image: url("https://cdn.discordapp.com/attachments/920268099234713653/929370584603832400/walpaper.jpg");
  position: absolute;
  min-width: 100%;
  min-height: 100%;
  background-size: cover;
  background-position: center;
}
button[type="submit"]:hover {
  background-color: gray;
  font-family: "Cursive";
}
button[type="submit"] {
  background-color: black;
  color: white;
  margin-top: 3%;
  font-family: "Cursive";
  border: 3px black solid;
  border-radius: 15px;
  width: 100%;
  font-size: 120%;
}

label {
  color: aliceblue;
  font-family: "Monospace";
  text-align: "center";
  height: auto;
}
a {
  font-family: "Merriweather", serif;
  margin-left: 1%;
}
input.data {
  width: 97%;
  border: 3px solid black;
  border-radius: 15px;
}
select {
  width: 97%;
  border: 3px solid black;
  border-radius: 15px;
}
h1 {
  color: aliceblue;
}
</style>