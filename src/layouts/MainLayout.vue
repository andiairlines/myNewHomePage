<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated class="bg-primary text-white">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar
            v-if="!isLoggedOn"
            icon="voice_over_off"
            size="60px"
            @click="isLoggedOn = true"
          >
            <q-tooltip class="bg-amber text-black shadow-4" :offset="[10, 10]"
              >log on for full site access</q-tooltip
            >
            <q-icon name="chevron_left" color="yellow" />
          </q-avatar>

          <q-avatar
            v-if="isLoggedOn"
            icon="record_voice_over"
            size="60px"
            @click="isLoggedOn = false"
          >
            <q-tooltip class="bg-amber text-black shadow-4" :offset="[10, 10]"
              >log off</q-tooltip
            >
          </q-avatar>

          <center>
            <span
              ><q-tooltip
                class="bg-amber text-black shadow-4"
                :offset="[10, 10]"
                >English</q-tooltip
              >
              Welcome </span
            >-
            <span
              ><q-tooltip
                class="bg-amber text-black shadow-4"
                :offset="[10, 10]"
                >Ich kann auch Hochdeutsch ;)</q-tooltip
              >
              Gunn Dach</span
            >
            -
            <span
              ><q-tooltip
                class="bg-amber text-black shadow-4"
                :offset="[10, 10]"
                >Hindi</q-tooltip
              >
              स्वागत है</span
            >
          </center></q-toolbar-title
        >
      </q-toolbar>
    </q-header>

    <q-page-container>
      <div>
        <q-splitter v-model="splitterModel">
          <template v-slot:before>
            <q-tabs v-model="tab" vertical class="text-teal">
              <q-tab
                name="messages"
                icon="question_answer"
                label="get in touch"
                @click="unreadMessages = 0"
              >
                <q-badge v-if="unreadMessages > 0" color="red" floating>{{
                  unreadMessages
                }}</q-badge>
              </q-tab>
              <q-tab name="heritage" icon="history_edu" label="Heritage" />
              <q-tab name="lab" icon="biotech" label="Lab" size="60px" />
            </q-tabs>
          </template>

          <template v-slot:after>
            <q-tab-panels
              v-model="tab"
              animated
              swipeable
              vertical
              transition-prev="jump-up"
              transition-next="jump-up"
            >
              <q-tab-panel name="messages">
                <div class="q-pa-md row justify-center">
                  <div style="width: 100%; max-width: 400px">
                    <q-chat-message
                      name="Andi"
                      avatar="~assets/andi.jpg"
                      :text="['Hi, I\'m Andreas Moser. SAP Architect']"
                      sent
                    />
                    <q-chat-message
                      v-if="!isLoggedOn"
                      name="Andi"
                      avatar="~assets/andi.jpg"
                      :text="['Log on to get in touch']"
                      sent
                    />
                    <q-chat-message
                      v-if="isLoggedOn"
                      name="Andi"
                      avatar="~assets/andi.jpg"
                      sent
                    >
                      <DIV
                        >Chat feature coming soon
                        <q-icon name="sentiment_very_satisfied"
                      /></DIV>
                      <DIV>Meanwhile use ...</DIV>

                      <div>
                        <A
                          HREF="https://www.linkedin.com/in/andreasmoser3/"
                          target="_BLANK"
                        >
                          <img
                            src="~assets/LinkedIn-Blue-14.png"
                            class="my-emoji"
                        /></A>
                      </div>
                      <div>
                        <a
                          href="https://www.xing.com/profile/Andreas_Moser3"
                          target="_blank"
                        >
                          <q-img src="~assets/Xing-Logo.png" />
                        </a>
                      </div>
                    </q-chat-message>
                    <q-chat-message
                      v-if="!isLoggedOn"
                      name="You"
                      avatar="~assets/icon-record_voice_over_off.png"
                    >
                      <q-spinner-dots size="2rem" />
                    </q-chat-message>
                    <q-chat-message
                      v-if="isLoggedOn"
                      name="You"
                      avatar="~assets/icon-record_voice_over.png"
                    >
                      <q-spinner-dots size="2rem" />
                    </q-chat-message>
                  </div>
                </div>
                <div class="q-pa-md q-gutter-md justify-center">
                  <q-card
                    class="my-card text-black"
                    style="
                      background: radial-gradient(
                        circle,
                        #35a2ff 0%,
                        #014a88 100%
                      );

                      width: 120px;
                    "
                  >
                  </q-card>
                </div>
              </q-tab-panel>

              <q-tab-panel name="cv">
                <div class="q-px-lg q-py-md">
                  <q-chat-message
                    v-if="!isLoggedOn"
                    name="Andi"
                    avatar="~assets/andi.jpg"
                    :text="['Log on to access this page']"
                    sent
                  />

                  <q-timeline color="secondary" v-if="isLoggedOn">
                    <q-timeline-entry heading>
                      Timeline heading
                    </q-timeline-entry>

                    <q-timeline-entry
                      title="Event Title"
                      subtitle="February 22, 1986"
                    >
                      <div>
                        Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit, sed do eiusmod tempor incididunt ut labore et
                        dolore magna aliqua. Ut enim ad minim veniam, quis
                        nostrud exercitation ullamco laboris nisi ut aliquip ex
                        ea commodo consequat. Duis aute irure dolor in
                        reprehenderit in voluptate velit esse cillum dolore eu
                        fugiat nulla pariatur. Excepteur sint occaecat cupidatat
                        non proident, sunt in culpa qui officia deserunt mollit
                        anim id est laborum.
                      </div>
                    </q-timeline-entry>

                    <q-timeline-entry
                      title="Event Title"
                      subtitle="February 21, 1986"
                      icon="delete"
                    >
                      <div>
                        Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit, sed do eiusmod tempor incididunt ut labore et
                        dolore magna aliqua. Ut enim ad minim veniam, quis
                        nostrud exercitation ullamco laboris nisi ut aliquip ex
                        ea commodo consequat. Duis aute irure dolor in
                        reprehenderit in voluptate velit esse cillum dolore eu
                        fugiat nulla pariatur. Excepteur sint occaecat cupidatat
                        non proident, sunt in culpa qui officia deserunt mollit
                        anim id est laborum.
                      </div>
                    </q-timeline-entry>

                    <q-timeline-entry heading>
                      November, 2017
                    </q-timeline-entry>

                    <q-timeline-entry
                      title="Event Title"
                      subtitle="February 22, 1986"
                      avatar="https://cdn.quasar.dev/img/avatar2.jpg"
                    >
                      <div>
                        Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit, sed do eiusmod tempor incididunt ut labore et
                        dolore magna aliqua. Ut enim ad minim veniam, quis
                        nostrud exercitation ullamco laboris nisi ut aliquip ex
                        ea commodo consequat. Duis aute irure dolor in
                        reprehenderit in voluptate velit esse cillum dolore eu
                        fugiat nulla pariatur. Excepteur sint occaecat cupidatat
                        non proident, sunt in culpa qui officia deserunt mollit
                        anim id est laborum.
                      </div>
                    </q-timeline-entry>

                    <q-timeline-entry
                      title="Event Title"
                      subtitle="February 22, 1986"
                    >
                      <div>
                        Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit, sed do eiusmod tempor incididunt ut labore et
                        dolore magna aliqua. Ut enim ad minim veniam, quis
                        nostrud exercitation ullamco laboris nisi ut aliquip ex
                        ea commodo consequat. Duis aute irure dolor in
                        reprehenderit in voluptate velit esse cillum dolore eu
                        fugiat nulla pariatur. Excepteur sint occaecat cupidatat
                        non proident, sunt in culpa qui officia deserunt mollit
                        anim id est laborum.
                      </div>
                    </q-timeline-entry>

                    <q-timeline-entry
                      title="Event Title"
                      subtitle="February 22, 1986"
                      color="orange"
                      icon="done_all"
                    >
                      <div>
                        Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit, sed do eiusmod tempor incididunt ut labore et
                        dolore magna aliqua. Ut enim ad minim veniam, quis
                        nostrud exercitation ullamco laboris nisi ut aliquip ex
                        ea commodo consequat. Duis aute irure dolor in
                        reprehenderit in voluptate velit esse cillum dolore eu
                        fugiat nulla pariatur. Excepteur sint occaecat cupidatat
                        non proident, sunt in culpa qui officia deserunt mollit
                        anim id est laborum.
                      </div>
                    </q-timeline-entry>

                    <q-timeline-entry
                      title="Event Title"
                      subtitle="February 22, 1986"
                    >
                      <div>
                        Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit, sed do eiusmod tempor incididunt ut labore et
                        dolore magna aliqua. Ut enim ad minim veniam, quis
                        nostrud exercitation ullamco laboris nisi ut aliquip ex
                        ea commodo consequat. Duis aute irure dolor in
                        reprehenderit in voluptate velit esse cillum dolore eu
                        fugiat nulla pariatur. Excepteur sint occaecat cupidatat
                        non proident, sunt in culpa qui officia deserunt mollit
                        anim id est laborum.
                      </div>
                    </q-timeline-entry>

                    <q-timeline-entry
                      title="Event Title"
                      subtitle="February 22, 1986"
                    >
                      <div>
                        Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit, sed do eiusmod tempor incididunt ut labore et
                        dolore magna aliqua. Ut enim ad minim veniam, quis
                        nostrud exercitation ullamco laboris nisi ut aliquip ex
                        ea commodo consequat. Duis aute irure dolor in
                        reprehenderit in voluptate velit esse cillum dolore eu
                        fugiat nulla pariatur. Excepteur sint occaecat cupidatat
                        non proident, sunt in culpa qui officia deserunt mollit
                        anim id est laborum.
                      </div>
                    </q-timeline-entry>
                  </q-timeline>
                </div>
              </q-tab-panel>

              <q-tab-panel name="lab">
                <div class="text-h4 q-mb-md">The Laboratory</div>
                <p>
                  This site is built using
                  <A HREF="https://quasar.dev/" target="_blank"
                    >quasar framework
                  </A>
                  with
                  <A HREF="https://stackblitz.com" target="_blank">stackblitz</A
                  >, managed on
                  <A HREF="https://github.com/andiairlines/myHomePage"
                    >GitHub</A
                  >

                  and hosted through
                  <a href="https://aws.amazon.com/amplify/" target="_blank"
                    >AWS Amplify</a
                  >
                </p>
                <p>
                  <q-spinner-radio color="red" size="2em" />&emsp;cool stuff!
                </p>
                <P>
                  <div class="q-pa-md" style="max-width: 350px">
                    some useful Links:
                    <q-list dense bordered padding class="rounded-borders">
                      <q-item clickable v-ripple>
                        <q-item-section>
                          <A
                            HREF="https://gist.github.com/ricog/3c28ae9214fdff10e06247116d8a87ef"
                            >Deploy Quasar Framework using AWS Amplify
                            Console</A
                          >
                        </q-item-section></q-item
                      ><q-item>
                        <q-item-section>
                          <A
                            HREF="https://stackoverflow.com/questions/61797412/aws-amplify-build-settings"
                            >AWS Amplify Build Settings</A
                          ></q-item-section
                        ></q-item
                      ><q-item>
                        <q-item-section>
                          <A
                            HREF="https://github.com/aws-amplify/amplify-hosting/issues/313#issuecomment-611203327"
                            >Amplify not recognizing my artifact directory
                            during deployment (directory om my case: dist/spa)
                          </A></q-item-section
                        >
                      </q-item></q-list
                    >
                  </div></P
                >
              </q-tab-panel>

              <q-tab-panel name="heritage">
                <div class="col-6">
                  <a
                    href="https://mittelbollenbacher-chronik.de/home.html"
                    target="_blank"
                  >
                    <q-tooltip
                      class="bg-amber text-black shadow-4"
                      :offset="[10, 10]"
                      >Mittelbollenbach, Deutschland</q-tooltip
                    >
                    <q-img src="~assets/mittelbollenbach.jpg">
                      <div class="absolute-bottom text-subtitle1 text-center">
                        Von der Scholle ...
                      </div>
                    </q-img>
                  </a>
                </div>
                <P />
                <div class="col-6">
                  <a href="https://wikipedia.org/wiki/Varanasi" target="_blank">
                    <q-tooltip
                      class="bg-amber text-black shadow-4"
                      :offset="[10, 10]"
                      >Varanasi, Bharat</q-tooltip
                    >
                    <q-img src="~assets/varanasi.jpg">
                      <div class="absolute-top text-subtitle1 text-center">
                        ... in die Welt
                      </div>
                    </q-img>
                  </a>
                </div>
              </q-tab-panel>
            </q-tab-panels>
          </template>
        </q-splitter>
      </div>
    </q-page-container>
  </q-layout>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const unreadMessages = ref(2);
    const isLoggedOn = ref(false);

    return {
      tab: ref('CV'),
      splitterModel: ref(20),
      unreadMessages,
      isLoggedOn,
    };
  },
};
</script>
