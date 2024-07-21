<q-card
                    class="my-card text-black"
                    style="
                      background: radial-gradient(
                        circle,
                        #35a2ff 0%,
                        #014a88 100%
                      );
                    "
                  >
                    <q-card>
                      <q-card-section>
                        <q-input
                          standout="bg-teal text-white"
                          v-model="text"
                          label="Your E-Mail Adress"
                          type="email"
                        /><P />
                        <q-input
                          standout="bg-teal text-white"
                          v-model="text"
                          label="Your Message"
                        />
                      </q-card-section>
                    </q-card>
                  </q-card>