<template>
<v-row class="pl-10 pr-10">
      <v-col v-for="(video, n) in videos" :key="n" cols="3" class="mb-5 pl-8">
        <v-hover v-slot="{ hover }" open-delay="500">
          <div>
            <v-row dense
              ><v-img v-if="hover" :src="video.thumbnailwebp" contain></v-img>
              <v-img v-else :src="video.thumbnailjpg" contain></v-img>
            </v-row>
            <v-row class="mt-5" dense>
              <v-col :cols="2" class="pl-0 pr-0">
                <v-avatar size="40">
                  <v-img :src="video.avatar"></v-img> </v-avatar
              ></v-col>
              <v-col :cols="10" class="pl-0">
                <v-list-item-title style="white-space: pre-wrap; margin-bottom: -20px;" class="font-weight-bold"
                  >{{ video.title }}
                </v-list-item-title>
                <v-list-item-subtitle
                  class="pl-0"
                  style="color: #aaa; font-size: 15px"
                >
                  {{ video.channelName }}
                  <v-icon color="grey" size="14" class="ml-1">{{
                    "mdi-check-circle"
                  }}</v-icon>
                </v-list-item-subtitle>
                <v-list-item-subtitle
                  class="pl-0"
                  style="color: #aaa; font-size: 15px"
                >
                  {{ video.views }}
                  <v-icon color="grey" size="20" class="ml-0 mr-0">{{
                    "mdi-circle-small"
                  }}</v-icon>
                  {{ video.date }}
                </v-list-item-subtitle></v-col
              >
            </v-row>
          </div>
        </v-hover>
      </v-col>
    </v-row>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  data()
  {
    return {
          videos: [
        {
          title: "Punishing Beth Harmon's Beginner Mistakes",
          channelName: "Eric Rosen",
          views: "159 tuh vaatamist",
          date: "2 nädala eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/cZrLHid70OU/hq720.jpg?sqp=-oaymwEcCNAFEJQDSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLCIp1V-toSHfdgOstiKQpuexhdoEA",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/cZrLHid70OU/mqdefault_6s.webp?du=3000&sqp=CJ_j04IG&rs=AOn4CLBjzdgc3zCVztNJGn1d6LVIvTTgBA",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwniwcZwhfYKHQlcAuX6GwyY9bPXzVCXya650YQ1B=s68-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "Another amazing bet you will always win",
          channelName: "Quirkology",
          views: "436 tuh vaatamist",
          date: "4 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/ORAwmR-EIzI/hqdefault.jpg?sqp=-oaymwEcCOADEI4CSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLDN8R4qlVMc8bbSXkzFTQODIV0Mwg",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/ORAwmR-EIzI/mqdefault_6s.webp?du=3000&sqp=CLDf04IG&rs=AOn4CLBZQKgXoGoBDJbj3402u5H17QQ58g",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwngNpXHNoFYF7i_eKJ5pYhNgXCDQC2Gp2ZHVVHzi=s68-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "Useless Attack but Perfect Situation",
          channelName: "I AM OP",
          views: "159 tuh vaatamist",
          date: "2 nädala eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/jrX-sB7wKg0/hq720.jpg?sqp=-oaymwEcCNAFEJQDSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLDJtysdLwwhrCk7k7JQta9nPs2ksg",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/jrX-sB7wKg0/mqdefault_6s.webp?du=3000&sqp=CNXq04IG&rs=AOn4CLBqelGQ7n3WB7_3UogUmrIaLEj1cw",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwnhdiycToAA0FRxYVuhofSob-dNAUvhWZpLwvp4G=s68-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "2 USEC 1 Sharp 10",
          channelName: "IamForkman16",
          views: "2,2 tuh vaatamist",
          date: "2 kuu eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/_pp2KG5ibqY/hq720.jpg?sqp=-oaymwEcCNAFEJQDSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLBvxEw8b9V8znVQYFy-1QXkLB0sYw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/_pp2KG5ibqY/mqdefault_6s.webp?du=3000&sqp=CLqP1IIG&rs=AOn4CLDSH8SOcoDF71qP_iyZLfxqTHr_0w",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwniIey5ROn4XzyYiY5c1rmBft0DBNsotLmPQW4Mw=s68-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "NHL: Odd Puck Moments",
          channelName: "CanucksFan27",
          views: "2,8 mln vaatamist",
          date: "3 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/9fja71JCeBo/hq720.jpg?sqp=-oaymwEcCNAFEJQDSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLCiG_Q-7l346NjeHFNQtlYj-K2zGw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/9fja71JCeBo/mqdefault_6s.webp?du=3000&sqp=CITb04IG&rs=AOn4CLDW_yJWAN6WGbvnquQGI19PdWUZbQ",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwnjN_NIiughD4My-6cqI_JmKLJus6GVsBC1fjZ2h_A=s68-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "Заяц пойман ушастый",
          channelName: "Колян Механизатор",
          views: "1,9 mln vaatamist",
          date: "8 kuu eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/_tqkTQxJE-w/hq720.jpg?sqp=-oaymwEcCNAFEJQDSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLB_E5OR86LcuVZADpmnxBWOZ4GFrg",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/_tqkTQxJE-w/mqdefault_6s.webp?du=3000&sqp=CLDu04IG&rs=AOn4CLCKus81AEA6VwvJHiaA_JcEJ_ufRg",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwnht7tyHOEICa-EfX8Bp-JeYzlqepKOLDRczSOX_gQ=s68-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "How to pick up a new car 🚗 ✌️",
          channelName: "Oliver Amon",
          views: "35 mln vaatamist",
          date: "2 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/t8eZPUcaHEY/hqdefault.jpg?sqp=-oaymwEcCOADEI4CSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLAUH-QHgbJBHFfeFa6yArpJ5qOdkA",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/t8eZPUcaHEY/mqdefault_6s_480x270.webp?du=3000&sqp=COTb04IG&rs=AOn4CLCx3piMW0KH6gXSiOggSGFMmeg1Iw",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwniCkqt6FbMA37Sji5R5oZV99QgEPi0RvA6x7mUqiJY=s68-c-k-c0x00ffffff-no-rj"
        },
        {
          title: 'Playing CSGO at night',
          channelName: "NeichingMaster",
          views: "769 tuhat vaatamist",
          date: "6 päeva eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/qqgiKN-3cuY/hq720.jpg?sqp=-oaymwEcCNAFEJQDSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLCmYOi2-GNkaxs8VsTY7lgKTBcEUg",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/NC9rakYWg9E/mqdefault_6s.webp?du=3000&sqp=CM6Q1IIG&rs=AOn4CLCCxGR2Zv2VD3C-utLS1niubhbiCw",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwniX4ImMNficN1nh-rKkY6ac-2JoPmKWTKbWDrM7eYA=s68-c-k-c0x00ffffff-no-rj"
        },
                {
          title: "Punishing Beth Harmon's Beginner Mistakes",
          channelName: "Eric Rosen",
          views: "159 tuh vaatamist",
          date: "2 nädala eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/cZrLHid70OU/hq720.jpg?sqp=-oaymwEcCNAFEJQDSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLCIp1V-toSHfdgOstiKQpuexhdoEA",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/cZrLHid70OU/mqdefault_6s.webp?du=3000&sqp=CJ_j04IG&rs=AOn4CLBjzdgc3zCVztNJGn1d6LVIvTTgBA",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwniwcZwhfYKHQlcAuX6GwyY9bPXzVCXya650YQ1B=s68-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "Another amazing bet you will always win",
          channelName: "Quirkology",
          views: "436 tuh vaatamist",
          date: "4 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/ORAwmR-EIzI/hqdefault.jpg?sqp=-oaymwEcCOADEI4CSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLDN8R4qlVMc8bbSXkzFTQODIV0Mwg",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/ORAwmR-EIzI/mqdefault_6s.webp?du=3000&sqp=CLDf04IG&rs=AOn4CLBZQKgXoGoBDJbj3402u5H17QQ58g",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwngNpXHNoFYF7i_eKJ5pYhNgXCDQC2Gp2ZHVVHzi=s68-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "Useless Attack but Perfect Situation",
          channelName: "I AM OP",
          views: "159 tuh vaatamist",
          date: "2 nädala eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/jrX-sB7wKg0/hq720.jpg?sqp=-oaymwEcCNAFEJQDSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLDJtysdLwwhrCk7k7JQta9nPs2ksg",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/jrX-sB7wKg0/mqdefault_6s.webp?du=3000&sqp=CNXq04IG&rs=AOn4CLBqelGQ7n3WB7_3UogUmrIaLEj1cw",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwnhdiycToAA0FRxYVuhofSob-dNAUvhWZpLwvp4G=s68-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "2 USEC 1 Sharp 10",
          channelName: "IamForkman16",
          views: "2,2 tuh vaatamist",
          date: "2 kuu eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/_pp2KG5ibqY/hq720.jpg?sqp=-oaymwEcCNAFEJQDSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLBvxEw8b9V8znVQYFy-1QXkLB0sYw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/_pp2KG5ibqY/mqdefault_6s.webp?du=3000&sqp=CLqP1IIG&rs=AOn4CLDSH8SOcoDF71qP_iyZLfxqTHr_0w",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwniIey5ROn4XzyYiY5c1rmBft0DBNsotLmPQW4Mw=s68-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "NHL: Odd Puck Moments",
          channelName: "CanucksFan27",
          views: "2,8 mln vaatamist",
          date: "3 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/9fja71JCeBo/hq720.jpg?sqp=-oaymwEcCNAFEJQDSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLCiG_Q-7l346NjeHFNQtlYj-K2zGw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/9fja71JCeBo/mqdefault_6s.webp?du=3000&sqp=CITb04IG&rs=AOn4CLDW_yJWAN6WGbvnquQGI19PdWUZbQ",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwnjN_NIiughD4My-6cqI_JmKLJus6GVsBC1fjZ2h_A=s68-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "Заяц пойман ушастый",
          channelName: "Колян Механизатор",
          views: "1,9 mln vaatamist",
          date: "8 kuu eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/_tqkTQxJE-w/hq720.jpg?sqp=-oaymwEcCNAFEJQDSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLB_E5OR86LcuVZADpmnxBWOZ4GFrg",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/_tqkTQxJE-w/mqdefault_6s.webp?du=3000&sqp=CLDu04IG&rs=AOn4CLCKus81AEA6VwvJHiaA_JcEJ_ufRg",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwnht7tyHOEICa-EfX8Bp-JeYzlqepKOLDRczSOX_gQ=s68-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "How to pick up a new car 🚗 ✌️",
          channelName: "Oliver Amon",
          views: "35 mln vaatamist",
          date: "2 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/t8eZPUcaHEY/hqdefault.jpg?sqp=-oaymwEcCOADEI4CSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLAUH-QHgbJBHFfeFa6yArpJ5qOdkA",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/t8eZPUcaHEY/mqdefault_6s_480x270.webp?du=3000&sqp=COTb04IG&rs=AOn4CLCx3piMW0KH6gXSiOggSGFMmeg1Iw",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwniCkqt6FbMA37Sji5R5oZV99QgEPi0RvA6x7mUqiJY=s68-c-k-c0x00ffffff-no-rj"
        },
        {
          title: 'Playing CSGO at night',
          channelName: "NeichingMaster",
          views: "769 tuhat vaatamist",
          date: "6 päeva eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/qqgiKN-3cuY/hq720.jpg?sqp=-oaymwEcCNAFEJQDSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLCmYOi2-GNkaxs8VsTY7lgKTBcEUg",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/NC9rakYWg9E/mqdefault_6s.webp?du=3000&sqp=CM6Q1IIG&rs=AOn4CLCCxGR2Zv2VD3C-utLS1niubhbiCw",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwniX4ImMNficN1nh-rKkY6ac-2JoPmKWTKbWDrM7eYA=s68-c-k-c0x00ffffff-no-rj"
        }
      ]
      }
  },
  components: {
    Logo,
    VuetifyLogo

  }
}
</script>
