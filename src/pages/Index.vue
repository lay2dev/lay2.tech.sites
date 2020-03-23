<template>
  <q-page class="flex flex-center page text-grey">
    <q-card square class="bg-dark desktop-hide shadow-24 q-ma-md q-pa-md">
      Sorry for the inconvenience, but the mobile version is under development. Please visit with desktop browser to get the best experience.
    </q-card>
    <q-card square class="terminal mobile-hide shadow-24 q-pa-md">
      <q-responsive class="wrapper" :ratio="16/9">
        <div class="column justify-between">
          <div class="header q-pa-xs row items-center justify-between">
            <q-img
              class="cursor-pointer"
              src="../assets/lay2-text.svg"
              width="72px"
              @click="tab='home'"
            />
            <q-tabs
              class="text-accent"
              v-model="tab"
              dense
              active-color="warning"
              indicator-color="dark"
            >
              <q-tab :ripple="false" name="home" label="Home" />
              <q-tab :ripple="false" name="prod" label="Products" />
              <q-tab :ripple="false" name="news" label="News" />
              <q-tab :ripple="false" name="team" label="Team" />
              <q-tab :ripple="false" name="join" label="Join US" />
            </q-tabs>
          </div>
          <div class="content scroll no-scrollbar col">
            <!-- HOME TAB -->
            <div v-show="tab==='home'" class="column home">
              <span class="q-mt-md">
                <q-icon name="las la-angle-right" />
                <span class="text-white">lay2 dev</span>
              </span>
              <span class="q-mt-md">
                -- make <span class="text-primary">efforts</span>
                to <span class="text-secondary">lower user barriers</span>
              </span>
              <span>
                -- create <span class="text-primary">value</span>
                with <span class="text-secondary">blockchain technology</span>
              </span>
              <span>
                -- connect <span class="text-primary">crytpos</span>
                with <span class="text-secondary">daily life</span>
              </span>
              <span class="q-mt-md">
                <q-icon name="las la-angle-right" />
                <span class="text-white">lay2 build</span>
                <span class="blink q-ml-xs">_</span>
              </span>
            </div>
            <!-- PRODUCTS TAB -->
            <q-scroll-area v-show="tab==='prod'" class="full-height q-pb-sm column">
              <div class="q-mt-md cmd">
                <q-icon name="las la-angle-right" />
                <span class="text-white">CKB P-Wallet</span>
              </div>
              <div class="text-detail">
                <q-btn color="primary" flat label="ckb.pw" @click="openURL('https://ckb.pw')" />
                <q-btn color="primary" flat label="Github" @click="openURL('https://github.com/lay2dev/ckb.pw')" />
              </div>
              <div class="text-detail q-px-md">
                <span class="intro-text"> {{ $t('text_ckbpw_intro') }} </span>
              </div>
              <div class="q-mt-md cmd">
                <q-icon name="las la-angle-right" />
                <span class="text-white">PW-SDK</span>
              </div>
              <div class="text-detail">
                <q-btn color="primary" flat label="RFC" @click="openURL('https://talk.nervos.org/t/lay2-pw-sdk-build-dapps-on-ckb-and-run-them-everywhere/4289')" />
                <q-btn color="primary" flat label="Github" @click="openURL('https://github.com/lay2dev/pw-lock')" />
              </div>
              <div class="text-detail q-px-md">
                <span class="intro-text"> {{ $t('text_pwsdk_intro') }} </span>
              </div>
              <div class="q-mt-md cmd">
                <q-icon name="las la-angle-right" />
                <span class="text-white">Nervos DAO Pro</span>
              </div>
              <div class="text-detail">
                <q-btn color="primary" flat label="nervosdao.pro" @click="openURL('#')" />
                <q-btn color="primary" flat label="Github" @click="openURL('#')" />
              </div>
              <div class="text-detail q-px-md">
                <span class="intro-text"> {{ $t('text_daopro_intro') }} </span>
              </div>
            </q-scroll-area>
            <!-- NEWS TAB -->
            <q-scroll-area v-show="tab==='news'" class="full-height q-pb-sm column">
              <div class="q-mt-md cmd">
                <q-icon name="las la-angle-right" />
                <span class="text-white">Grant Approved By Nervos Foundation</span>
              </div>
              <div class="text-detail q-px-md">
                <div>[ 2020-03-12 ]</div>
                <div class="text-secondary"> {{ $t('text_grant_approved') }} </div>
              </div>
              <q-btn class="self-start" color="primary" flat label="Announcement" @click="openURL('https://medium.com/nervosnetwork/ecosystem-grants-lay2-project-awarded-6th-nervos-grant-c2ee081e3c5b')" />
              <div class="q-mt-md cmd">
                <q-icon name="las la-angle-right" />
                <span class="text-white">AMA Talk: Frank with Victor@AlphaWallet</span>
              </div>
              <div class="text-detail q-px-md">
                <div>[ 2020-02-18 ]</div>
                <div class="text-secondary"> {{ $t('text_ama_bilibili') }} </div>
              </div>
              <q-btn class="self-start" color="primary" flat label="Video On BiliBili" @click="openURL('https://www.bilibili.com/video/av89908015#')" />
            </q-scroll-area>
            <!-- TEAM TAB -->
            <div v-show="tab==='team'" class="row full-height items-center justify-around">
              <q-card class="member-card text-grey-4">
                <q-item>
                  <q-item-section avatar>
                    <q-avatar>
                      <img src="https://cdn.quasar.dev/img/boy-avatar.png" />
                    </q-avatar>
                  </q-item-section>
                  <q-item-section>
                    <q-item-label class="text-h6">Frank</q-item-label>
                    <q-item-label class="text-subtitle">PM · FE</q-item-label>
                  </q-item-section>
                </q-item>
                <q-separator inset dark />
                <q-card-section>
                  <ul>
                    <li> PKU · CS </li>
                    <li> Entrepreneur </li>
                  </ul>
                </q-card-section>
              </q-card>
              <q-card class="member-card text-grey-4">
                <q-item>
                  <q-item-section avatar>
                    <q-avatar>
                      <img src="https://cdn.quasar.dev/img/boy-avatar.png" />
                    </q-avatar>
                  </q-item-section>
                  <q-item-section>
                    <q-item-label class="text-h6">John</q-item-label>
                    <q-item-label class="text-subtitle">RD · BE</q-item-label>
                  </q-item-section>
                </q-item>
                <q-separator inset dark />
                <q-card-section>
                  <ul>
                    <li> PKU · CS </li>
                    <li> Entrepreneur </li>
                  </ul>
                </q-card-section>
              </q-card>
            </div>
            <!-- TAB JOIN US -->
            <div v-show="tab==='join'" class="column full-height justify-center items-center">
              <span class="q-mt-md text-secondary text-h5" style="max-width: 70%">
                <div class="text-center">{{$t('text_join_us')}}</div>
              </span>
              <span class="q-mt-md cmd">
                <span>{{$t('label_contact')}}:  <a href="mailto://join@lay2.dev" class="q-ml-sm text-warning"> join@lay2.dev </a></span>
              </span>
              <span class="q-mt-md q-pa-md text-detail">
                <span>{{$t('text_join_discord')}}</span>
              </span>
              </div>
          </div>
          <div class="footer row items-center justify-between">
            <div class="row items-center q-gutter-xs">
              <q-btn color="secondary" dense flat @click="openURL('https://nervos.org')">Nervos</q-btn>
              <strong>·</strong>
              <q-btn color="secondary" dense flat @click="openURL('https://docs.ckb.dev')">CKB.DEV</q-btn>
            </div>
            <div class="row items-center q-gutter-xs">
              <q-btn color="secondary" flat dense icon="lab la-github"
                @click="openURL('https://github.com/lay2dev')"
              />
              <strong>·</strong>
              <q-btn color="secondary" flat dense icon="lab la-discord"
                @click="openURL('https://discord.gg/ZuFQGCx')"
              />
              <strong>·</strong>
              <q-btn color="secondary" flat dense icon="lab la-twitter"
                @click="openURL('#')" />
            </div>
          </div>
        </div>
      </q-responsive>
    </q-card>
  </q-page>
</template>

<script>
import { openURL } from "quasar";
export default {
  name: "Index",
  data() {
    return {
      tab: "home"
    };
  },
  methods: {
    openURL: function(url) {
      if(url === '#') {
        this.$q.notify({
          message: 'comming soon',
          color: 'accent',
          timeout: 1500,
          position: 'center'
        })
      } else {
        openURL(url)
      }
    }
  }
};
</script>
<style lang="scss" scoped>
.page {
  background: $main-grey;
}
.terminal {
  background: $dark;
  width: 75%;
  min-width: 1000px;
  max-width: 1200px;
}
.wrapper:before {
  content: " ";
  display: block;
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  opacity: 0.05;
  background-image: url("../assets/lay2-shape.svg");
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: center;
}
.home {
  font-size: 3em;
  padding-top: 24px;
}
.cmd {
  padding-top: 24px;
  font-size: 1.8em;
}
.member-card {
  min-width: 280px;
  background-color: $main-grey;
}

.blink {
  animation: blinker 1s step-start infinite;
}
@keyframes blinker {
  50% {
    opacity: 0;
  }
}
.text-detail {
  font-size: 1.2em;
  max-width: 75%;
}
</style>