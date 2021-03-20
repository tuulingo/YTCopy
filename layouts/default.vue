<template>
  <v-app dark>
    <v-navigation-drawer class="v-navigation-drawercontent"
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <div v-if="miniVariant">
        <v-list>
          <v-list-item
            v-for="(miniVariantItem, i) in miniVariantItems"
            :key="i"
            :to="miniVariantItem.to"
            router
            exact
          >
            <v-list-item-action class="mt-6 pr-2">
              <v-icon class="pb-2 pr-2">{{ miniVariantItem.icon }}</v-icon>
              <!-- <p class="caption ml-2 pt-6">
                {{ miniVariantItem.title }}
              </p> -->
            </v-list-item-action>
          </v-list-item>
        </v-list>
      </div>
      <div v-else>
        <v-list>
          <v-list-item
            v-for="(mainItem, i) in mainItems"
            :key="i"
            :to="mainItem.to"
            router
            exact
          >
            <v-list-item-action class="ml-2">
              <v-icon>{{ mainItem.icon }}</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title class="body-2" v-text="mainItem.title" />
            </v-list-item-content>
          </v-list-item>
        </v-list>
        <v-divider></v-divider>
        <v-list>
          <v-list-item
            v-for="(categoryItem, i) in categoryItems"
            :key="i"
            :to="categoryItem.to"
            router
            exact
          >
            <v-list-item-action class="ml-2">
              <v-icon>{{ categoryItem.icon }}</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title class="body-2" v-text="categoryItem.title" />
            </v-list-item-content>
          </v-list-item>
        </v-list>
        <v-divider></v-divider>
        <p
          v-if="!miniVariant"
          class="subtitle-2 grey--text"
          style="margin: 7% 0px -3% 25px"
        >
          TELLIMUSED
        </p>
        <v-list>
          <v-list-item
            v-for="(subscriptionItem, i) in computedObj"
            :key="i"
            :to="subscriptionItem.to"
            router
            exact
          >
            <v-list-item-avatar class="ml-2" size="25">
              <v-img :src="subscriptionItem.icon"></v-img>
            </v-list-item-avatar>
            <v-list-item-content class="ml-3">
              <v-list-item-title
                class="body-2"
                v-text="subscriptionItem.title"/>
            </v-list-item-content>
            <v-icon v-if="subscriptionItem.notification === 'notification'" color="blue">{{"mdi-circle-small"}}</v-icon>
            <v-icon v-if="subscriptionItem.notification === 'live'" color="red" size="20">{{"mdi-access-point"}}</v-icon>
          </v-list-item>
        </v-list>
        <v-divider></v-divider>
        <p
          v-if="!miniVariant"
          class="subtitle-2 grey--text"
          style="margin: 7% 0px -3% 25px"
        >
          ROHKEM YOUTUBE'IST
        </p>
        <v-list>
          <v-list-item
            v-for="(moreAbYTItem, i) in moreAbYTItems"
            :key="i"
            :to="moreAbYTItem.to"
            router
            exact
          >
            <v-list-item-action class="ml-2">
              <v-icon>{{ moreAbYTItem.icon }}</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title class="body-2" v-text="moreAbYTItem.title" />
            </v-list-item-content>
          </v-list-item>
        </v-list>
        <v-divider></v-divider>
        <v-list>
          <v-list-item
            v-for="(moreAbYTItem2, i) in moreAbYTItems2"
            :key="i"
            :to="moreAbYTItem2.to"
            router
            exact
          >
            <v-list-item-action class="ml-2">
              <v-icon>{{ moreAbYTItem2.icon }}</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title class="body-2" v-text="moreAbYTItem2.title" />
            </v-list-item-content>
          </v-list-item>
        </v-list>
        <v-divider></v-divider>
        <div class="ml-6 mr-8 mt-2" style="letter">
          <a href="http://localhost:3000/" class="link mr-1 text--secondary caption">Teave</a>
          <a href="http://localhost:3000/" class="link mr-1 text--secondary caption">Press</a>
          <a href="http://localhost:3000/" class="link text--secondary caption">Autoriõigused</a>
          <a href="http://localhost:3000/" class="link text--secondary caption">Võtke meiega ühendust</a>
          <a href="http://localhost:3000/" class="link text--secondary mr-1 caption">Sisuloojad</a>
          <a href="http://localhost:3000/" class="link text--secondary mr-1 caption">Reklaam</a>
          <a href="http://localhost:3000/" class="link text--secondary caption">Arendajad</a>
        </div>
        <div class="ml-6 mr-8 mt-2">
          <a href="http://localhost:3000/" class="link text--secondary mr-1 caption">Tingimused</a>
          <a href="http://localhost:3000/" class="link text--secondary caption">Privaatsus</a>
          <a href="http://localhost:3000/" class="link text--secondary mr-9 caption">Eeskirjad ja ohutus</a>
          <a href="http://localhost:3000/" class="link text--secondary caption">Kuidas YouTube toimib?</a>
          <a href="http://localhost:3000/" class="link text--secondary caption">Proovige uusi funktsioone</a>
        </div>
        <p class="ml-6 mt-4 body-2 darken" style="color: #757575">© 2021 Google LLC</p>
      </div>
    </v-navigation-drawer>
    
    <v-app-bar :clipped-left="clipped" fixed app dark>
       <v-app-bar-nav-icon @click.stop="miniVariant = !miniVariant" />
      <a class="text-decoration-none white--text" href="/">
        <v-img
          class="white--text"
          width="25"
          src="https://upload.wikimedia.org/wikipedia/commons/e/e1/YouTube_play_buttom_icon_%282013-2017%29.svg"
          max-height="100px"
          max-width="300px"
        >
        </v-img>
      </a>
      <a>
        <v-toolbar-title class="link text--primary ml-1" v-text="title" />
      </a>
      <sup class="grey--text lighten-1">EE</sup>
      <v-spacer />
      <v-container>
        <v-row justify="center">
          <input
            class="search-bar--input rounded-0"
            type="text"
            placeholder="Otsige"
          />
          <v-tooltip bottom>
            <template v-slot:activator="{ on, attrs }">
              <v-btn
                class="search-bar--button grey--text darken-3 grey rounded-0"
                v-bind="attrs"
                v-on="on"
              >
                <v-icon>mdi-magnify</v-icon>
              </v-btn>
            </template>
            <span>Otsige</span>
          </v-tooltip>
          <v-tooltip bottom>
            <template v-slot:activator="{ on, attrs }">
              <v-icon class="ml-4" v-bind="attrs" v-on="on">
                mdi-microphone
              </v-icon>
            </template>
            <span>Häälotsing</span>
          </v-tooltip>
        </v-row>
      </v-container>
        <v-tooltip  bottom>
            <template v-slot:activator="{ on, attrs }">
              <v-icon class="mr-8" v-bind="attrs" v-on="on">
                mdi-video-plus
              </v-icon>
            </template>
            <span>Märguanded</span>
          </v-tooltip>
          <v-tooltip bottom>
            <template v-slot:activator="{ on, attrs }">
              <v-icon class="mr-8" v-bind="attrs" v-on="on">
                mdi-grid
              </v-icon>
            </template>
            <span>YouTube-i rakendused</span>
          </v-tooltip>
          <v-tooltip bottom>
            <template v-slot:activator="{ on, attrs }">
              <v-icon class="mr-8" v-bind="attrs" v-on="on">
                mdi-bell
              </v-icon>
            </template>
            <span>Loomine</span>
          </v-tooltip>
       <v-menu max-width="400px" offset-y>
        <template v-slot:activator="{ on, attrs }">
            <v-avatar color="blue" size="40">
                  <v-btn color="brown" height="100%" width="100%" rounded v-bind="attrs" v-on="on">
                    <span class="white--text">OT</span> 
                  </v-btn>           
            </v-avatar>        
        </template>
        <v-list min-width="300px" max-width="300px" class="pr-4">
          <v-row class="ml-3 mb-3 mt-4">
          <v-avatar size="40">
              <v-btn color="brown" height="100%" width="100%" rounded v-bind="attrs" v-on="on">
                <span class="white--text">OT</span> 
              </v-btn>           
          </v-avatar>
          <p class="font-weight-bold ml-5">
            Oliver Tuuling
          </p>
          <a href="http://localhost:3000/" class="ml-15 mt-n3 link caption">Google'i konto haldamine</a>
          </v-row>
          <v-divider></v-divider>
          <v-list >
          <v-list-item
            v-for="(userItem1, i) in userItems1"
            :key="i"
            :to="userItem1.to"
            router
            exact
            class="mb-n1"
          >
            <v-list-item-action class="ml-2">
              <v-icon>{{ userItem1.icon }}</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title class="body-2" v-text="userItem1.title" />
            </v-list-item-content>
            <v-icon v-if="userItem1.more === 'true'">{{"mdi-chevron-right"}}</v-icon>
          </v-list-item>
        </v-list>
        <v-divider></v-divider>
        <v-list >
          <v-list-item
            v-for="(userItem2, i) in userItems2"
            :key="i"
            :to="userItem2.to"
            router
            exact
            class="mb-n1"
          >
            <v-list-item-action class="ml-2">
              <v-icon>{{ userItem2.icon }}</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title class="body-2" v-text="userItem2.title" />
            </v-list-item-content>
            <v-icon v-if="userItem2.more === 'true'">{{"mdi-chevron-right"}}</v-icon>
          </v-list-item>
        </v-list>
        <v-divider></v-divider>
          <v-list class="mb-n2 ml-5">
            <v-list-item-action class="ml-2">
              <v-list-item-title class="body-2">Piiratud režiim: väljas</v-list-item-title>
            </v-list-item-action>
            <v-icon class="mt-2 mr-4 float-right">{{"mdi-chevron-right"}}</v-icon>
          </v-list>
        </v-list>
      </v-menu>
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<style lang="scss">
#no-background-hover::before {
  background-color: transparent !important;
}
.link {
  text-decoration: none;
  background-color: none;
}
::-webkit-scrollbar {
  width: 8px;
}
::-webkit-scrollbar-track {
  background: #363636;
}
::-webkit-scrollbar-thumb {
  background: #888;
}
::-webkit-scrollbar-thumb:hover {
  background: #555;
}
.search-bar--input {
  width: 30%;
  min-width: 200px;
  padding: 1rem;
  height: 1.7rem;
  background-color: #121212;
  color: white;
  border-width: 0.2px;
  border-style: solid;
}
.search-bar--input:focus {
  outline: #3ea6ff 1px solid;
}
.search-bar--button {
  height: auto !important;
  border-width: 1px !important;
  margin-left: 1px !important;
  border-style: solid !important;
}
</style>

<script>
export default {
  data() {
    return {
      clipped: true,
      drawer: false,
      fixed: false,
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "YouTube",
      limit: 7,
      userItems1: [
        {
          icon: "mdi-account-box",
          title: "Teie kanal",
          to: "/30",
          more: "false"
        },
        {
          icon: "mdi-currency-usd-circle",
          title: "Ostud ja liikmesused",
          to: "/31",
          more: "false"
        },
        {
          icon: "mdi-youtube-studio",
          title: "YouTube Studio",
          to: "/32",
          more: "false"
        },
        {
          icon: "mdi-account-box-multiple",
          title: "Vaheta kontot",
          to: "/33",
          more: "true"
        },
        {
          icon: "mdi-login-variant",
          title: "Logi välja",
          to: "/34",
          more: "false"
        },
      ],
      userItems2: [
        {
          icon: "mdi-theme-light-dark",
          title: "Välimus: tume",
          to: "/35",
          more: "true"
        },
        {
          icon: "mdi-translate",
          title: "Keel: eesti",
          to: "/36",
          more: "true"
        },
        {
          icon: "mdi-earth",
          title: "Asukoht: Eesti",
          to: "/37",
          more: "true"
        },
        {
          icon: "mdi-cog",
          title: "Seaded",
          to: "/38",
          more: "false"
        },
        {
          icon: "mdi-shield-account",
          title: "Teie andmed YouTube'is",
          to: "/39",
          more: "false"
        },
                {
          icon: "mdi-help-circle",
          title: "Abi",
          to: "/40",
          more: "false"
        },
        {
          icon: "mdi-message-alert",
          title: "Saada tagasisidet",
          to: "/41",
          more: "false"
        },
        {
          icon: "mdi-keyboard",
          title: "Klaviatuuri otseteed",
          to: "/42",
          more: "false"
        },
      ],
      nextToUser: [
        {
          icon: "mdi-youtube",
          title: "YouTube Premium",
          to: "/20",
        },
        {
          icon: "mdi-youtube-gaming",
          title: "Mängud",
          to: "/21",
        },
        {
          icon: "mdi-access-point",
          title: "Otseülekanded",
          to: "/22",
        }
      ],
      moreAbYTItems: [
        {
          icon: "mdi-youtube",
          title: "YouTube Premium",
          to: "/20",
        },
        {
          icon: "mdi-youtube-gaming",
          title: "Mängud",
          to: "/21",
        },
        {
          icon: "mdi-access-point",
          title: "Otseülekanded",
          to: "/22",
        },
        {
          icon: "mdi-trophy",
          title: "Sport",
          to: "/23",
        },
      ],
      moreAbYTItems2: [
        {
          icon: "mdi-cog",
          title: "Seaded",
          to: "/24",
        },
        {
          icon: "mdi-flag",
          title: "Teavituste ajalugu",
          to: "/25",
        },
        {
          icon: "mdi-help-circle",
          title: "Abi",
          to: "/26",
        },
        {
          icon: "mdi-message-alert",
          title: "Saada tagasisidet",
          to: "/27",
        },
      ],
      miniVariantItems: [
        {
          icon: "mdi-home",
          title: "Avaleht",
          to: "/16",
          style1: "true",
        },
        {
          icon: "mdi-fire",
          title: "Populaarsed",
          to: "/17",
          style2: "true",
        },
        {
          icon: "mdi-youtube-subscription",
          title: "Tellimused",
          to: "/18",
          style3: "true",
        },
        {
          icon: "mdi-play-box-multiple",
          title: "Kogu",
          to: "/19",
          style4: "true",
        },
      ],
      mainItems: [
        {
          icon: "mdi-home",
          title: "Avaleht",
          to: "/",
        },
        {
          icon: "mdi-fire",
          title: "Populaarsed",
          to: "/1",
        },
        {
          icon: "mdi-youtube-subscription",
          title: "Tellimused",
          to: "/2",
        },
      ],
      categoryItems: [
        {
          icon: "mdi-play-box-multiple",
          title: "Kogu",
          to: "/3",
        },
        {
          icon: "mdi-history",
          title: "Ajalugu",
          to: "/4",
        },
        {
          icon: "mdi-play-box-outline",
          title: "Teie videod",
          to: "/6",
        },
        {
          icon: "mdi-clock",
          title: "Hiljem vaatamiseks",
          to: "/7",
        },
        {
          icon: "mdi-playlist-play",
          title: "Lemmikud",
          to: "/8",
        },
        {
          icon: "mdi-thumb-up",
          title: "Meeldinud videod",
          to: "/9",
        },
      ],
      subscriptionItems: [
        {
          icon:
            "https://yt3.ggpht.com/ytc/AAUvwngd7qBDc_fPLa_GX8aP9Jg-JGfxnQzDKcQSY9R5=s88-c-k-c0x00ffffff-no-rj",
          title: "NxrthNxrthPhvnk",
          to: "/10",
          notification: "live",
        },
        {
          icon:
            "https://yt3.ggpht.com/ytc/AAUvwnhfcPSEAkCaiyqHRz2Ku17-2vdrMSMAhEmwkcH1ew=s88-c-k-c0x00ffffff-no-rj",
          title: "Galaxy Goats",
          to: "/11",
          notification: null,
        },
        {
          icon:
            "https://yt3.ggpht.com/ytc/AAUvwnhozhITL_erhtQTAeA6picyI6lkoM7DFxclsbIV6g=s88-c-k-c0x00ffffff-no-rj",
          title: "MINDZ",
          to: "/12",
          notification: "notification",
        },
        {
          icon:
            "https://yt3.ggpht.com/ytc/AAUvwnjIX6V10Xcp4FD88moFajZBYXpy4VfxsIj6xQCYqA=s88-c-k-c0x00ffffff-no-rj",
          title: "DemoltionRanch",
          to: "/13",
          notification: "notification",
        },
        {
          icon:
            "https://yt3.ggpht.com/ytc/AAUvwngNpXHNoFYF7i_eKJ5pYhNgXCDQC2Gp2ZHVVHzi=s88-c-k-c0x00ffffff-no-rj",
          title: "Quirkology",
          to: "/14",
          notification: null,
        },
        {
          icon:
            "https://yt3.ggpht.com/ytc/AAUvwnhP_QDYastCi_7Zlr0nLtDXaqf5bbw79S6PF5pi=s88-c-k-c0x00ffffff-no-rj",
          title: "Hulltaat",
          to: "/15",
          notification: "notification",
        },
      ],
    };
  },
  computed:{
    computedObj(){
      return this.limit ? this.subscriptionItems.slice(0,this.limit) : this.subscriptionItems
    }
  }
};
</script>
