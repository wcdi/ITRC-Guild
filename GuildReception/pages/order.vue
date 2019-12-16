<template>
  <div>
    <div v-for="(content, index) in contents" :key="index">
      <div v-for="(item, index) in content.items" :key="index">
        <h1>{{item.quest}}</h1>
        <h2>{{item.remuneration}}</h2>
        <h2>{{item.time_limit}}</h2>
        <h3>{{item.main_monster}}</h3>
        <h3>{{item.requester}}</h3>
        <p>{{item.memo}}</p>
        <div v-for="detail in item.failure_condition" :key="detail">
          <h2>{{detail.details}}</h2>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      contents: [
        {
          items: [
            {
              quest: "世界の平和を守ってくれ",
              remuneration: "2500P",
              time_limit: "2019-12-31",
              conditions: [
                {
                  details: "無事にギルドシステムyを作ってくれ"
                }
              ],
              failure_condition: [
                {
                  details: "納期に間に合わない"
                },
                {
                  details: "hoge"
                }
              ],
              main_monster: "自分自身",
              requester: "安倍総理大臣",
              memo:
                "大変だ！今まさに国家を脅かそうとしていることが起きている。\nこれを完璧にできなかったらこの日本は終わりだ！\n頼むぞ！諸君！次回「やっぱりダメだったお...」",
              image: ""
            },
            {
              quest: "漆黒のニャンコ再来",
              remuneration: "100P",
              time_limit: "2020-02-01",
              conditions: [
                {
                  details: "ナルガクルガの討伐"
                }
              ],
              failure_condition: [
                {
                  details: "３回力つきる",
                  details: "途中で任務を放棄"
                }
              ],
              main_monster: "ナルガクルガ",
              requester: "ニャンコ",
              memo: "大変だにゃー！ナルガクルガがまた現れたにゃーん\n",
              image: ""
            }
          ]
        }
      ]
    };
  }
};
</script>