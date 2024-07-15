<template>
  <div class="q-pa-md q-gutter-sm">
    <q-banner :class="$q.dark.isActive ? 'bg-grey-9' : 'bg-grey-3'">
      <div style="font-size: 20px; font-weight: bold">
        현재 절약한 CO2: {{ co2count }}kg
      </div>
    </q-banner>

    <q-banner :class="$q.dark.isActive ? 'bg-grey-9' : 'bg-grey-3'">
      <template v-slot:avatar>
        <q-icon name="subway" color="green" />
      </template>
      대중교통 이용하기
      <template v-slot:action>
        <q-btn
          flat
          color="green"
          @click="showNotif(1.5)"
          label="Mission Complete"
        />
      </template>
    </q-banner>

    <q-banner :class="$q.dark.isActive ? 'bg-grey-9' : 'bg-grey-3'">
      <template v-slot:avatar>
        <q-icon name="outlet" color="green" />
      </template>
      안쓰는 콘센트 뽑기
      <template v-slot:action>
        <q-btn
          flat
          color="green"
          @click="showNotif(0.23)"
          label="Mission Complete"
        />
      </template>
    </q-banner>
    <q-banner :class="$q.dark.isActive ? 'bg-grey-9' : 'bg-grey-3'">
      <template v-slot:avatar>
        <q-icon name="local_drink" color="green" />
      </template>
      텀블러 사용하기
      <template v-slot:action>
        <q-btn
          flat
          color="green"
          @click="showNotif(0.23)"
          label="Mission Complete"
        />
      </template>
    </q-banner>
    <q-banner :class="$q.dark.isActive ? 'bg-grey-9' : 'bg-grey-3'">
      <template v-slot:avatar>
        <q-icon name="label" color="green" />
      </template>
      라벨 떼기
      <template v-slot:action>
        <q-btn
          flat
          color="green"
          @click="showNotif(0.241)"
          label="Mission Complete"
        />
      </template>
    </q-banner>
    <q-banner :class="$q.dark.isActive ? 'bg-grey-9' : 'bg-grey-3'">
      <template v-slot:avatar>
        <q-icon name="description" color="green" />
      </template>
      이면지 쓰기
      <template v-slot:action>
        <q-btn
          flat
          color="green"
          @click="showNotif(0.054)"
          label="Mission Complete"
        />
      </template>
    </q-banner>
    <q-banner :class="$q.dark.isActive ? 'bg-grey-9' : 'bg-grey-3'">
      <template v-slot:avatar>
        <q-icon name="restaurant" color="green" />
      </template>
      채식하기
      <template v-slot:action>
        <q-btn
          flat
          color="green"
          @click="showNotif(1.55)"
          label="Mission Complete"
        />
      </template>
    </q-banner>
    <q-banner :class="$q.dark.isActive ? 'bg-grey-9' : 'bg-grey-3'">
      <template v-slot:avatar>
        <q-icon name="stairs" color="green" />
      </template>
      계단 걷기
      <template v-slot:action>
        <q-btn
          flat
          color="green"
          @click="showNotif(0.16)"
          label="Mission Complete"
        />
      </template>
    </q-banner>
  </div>
</template>

<script>
import { ref } from "vue";
import { useQuasar } from "quasar";

export default {
  name: "Co2Count",
  setup() {
    const $q = useQuasar();
    const co2count = ref(0);

    const showNotif = (co2) => {
      co2count.value += co2;
      $q.notify({
        message: `${co2}kg만큼의 탄소를 줄였습니다!`,
        color: "primary",
        multiLine: true,
        avatar:
          "https://png.pngtree.com/png-vector/20231226/ourmid/pngtree-tree-isolated-on-white-png-image_11382993.png",
        actions: [
          {
            label: "Reply",
            color: "yellow",
            handler: () => {
              /* ... */
            },
          },
        ],
      });
    };

    return {
      co2count,
      showNotif,
    };
  },
};
</script>
