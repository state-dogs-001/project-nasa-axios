<template>
  <v-container>
    <v-card>
      <v-row>
        <v-col cols="4">
          <v-img :src="dataList.url" class="ml-4" />
          <hr style="width: 355px; margin-left: 16px; margin-top: 10px" />
          <p class="font-weight-light" style="margin-left: 16px">
            Credit : image from nasa (www.nasa.gov)
          </p>
        </v-col>
        <v-col cols="8">
          <h1>{{ dataList.title }}</h1>
          <hr style="width: 620px; margin-top: 10px; margin-bottom: 10px" />
          <h4>Date : {{ dataList.date }}</h4>
          <br />
          <p>{{ dataList.explanation }}</p>
        </v-col>
      </v-row>
    </v-card>
  </v-container>
</template>

<script>
import axios from "axios";
export default {
  data: () => {
    return {
      dataList: {},
    };
  },
  mounted() {
    axios({
      method: "GET",
      url:
        "https://api.nasa.gov/planetary/apod?api_key=daTLBdVyv7LlvH8bU7SEcpkdoTvPzeydwNMIzEiX",
    })
      .then((res) => {
        this.dataList = res.data;
      })
      .catch((err) => {
        console.log(err);
      });
  },
};
</script>
