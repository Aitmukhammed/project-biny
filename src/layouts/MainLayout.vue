<template>
  <div>
    <q-layout view="lHh Lpr fFr">


      <q-drawer
        v-model="drawer"
        show-if-above
        :mini="miniState"
        :width="320"
        :breakpoint="500"
        style="background-color:#252729;"
      >
      <q-scroll-area
      :thumb-style="thumbStyle"
      :bar-style="barStyle"
      style="height: 850px;"
    >
      <img src="../../public/icons/biny_icons/logo_biny.svg"
      class="logo_biny q-mt-md q-pl-md"
      :style="{ marginLeft: !miniState ? '0' : '-100px' }"
      />
      <q-btn
        flat
        @click="miniState = !miniState"
        round
        densex
        class="fixed-top-right q-mt-md"
        >
        <q-icon
          :name=" miniState ? 'img:/icons/biny_icons/menu.svg' : 'img:/icons/biny_icons/close_menu.svg'"
          :class="miniState ? 'menu_icon' : ''"
          @click="showDropdown"></q-icon>
      </q-btn>

      <q-list padding class="q-mt-xs">
        <q-btn-dropdown
          :icon="'img:/icons/biny_icons/van.svg'"
          label="Активные заказы"
          no-caps
          class="textMenu"
          style="width: 93%; align-items: flex-start; margin-left: 12px; padding-left: 5px; position: fixed;"
          :dropdown-icon="'img:/icons/biny_icons/dropdown.svg'"
          @click="showDropdown"
          >
        </q-btn-dropdown>

        <q-list  v-if="dropdownOpen && !miniState" style="position: relative; margin-top: 60px; ">
          <q-item clickable v-close-popup class="q-mt-sm" >
            <q-icon class="line q-pl-lg q-pt-sm" :name="'img:/icons/biny_icons/line1.svg'"></q-icon>
            <q-item-section>
              <q-item-label class="dropDownText q-pl-sm">На модерации</q-item-label>
            </q-item-section>
              <q-text class="dropDownText numberDropDownText q-mr-sm">22</q-text>
          </q-item>

          <q-item clickable v-close-popup class="q-mt-sm" >
            <q-icon class="line q-pl-lg q-pt-sm"  :name="'img:/icons/biny_icons/line2.svg'"></q-icon>
            <q-item-section>
              <q-item-label class="dropDownText q-pl-sm">Ожидает погрузки</q-item-label>
            </q-item-section>
              <q-text class="dropDownText numberDropDownText q-mr-sm">222</q-text>
          </q-item>

          <q-item clickable v-close-popup class="q-mt-sm" >
            <q-icon class="line q-pl-lg q-pt-sm"  :name="'img:/icons/biny_icons/line3.svg'"></q-icon>
            <q-item-section>
              <q-item-label class="dropDownText q-pl-sm">В пути</q-item-label>
            </q-item-section>
              <q-text class="dropDownText numberDropDownText q-mr-sm">22</q-text>
          </q-item>

          <q-item clickable v-close-popup class="q-mt-sm" >
            <q-icon class="line q-pl-lg q-pt-sm"  :name="'img:/icons/biny_icons/line4.svg'"></q-icon>
            <q-item-section>
              <q-item-label class="dropDownText q-pl-sm">Ожидает завершения</q-item-label>
            </q-item-section>
              <q-text class="dropDownText numberDropDownText q-mr-sm">22</q-text>
          </q-item><br>
          <q-separator class="bottom_line q-ml-sm q-mr-sm" size="0.5px" style="margin-bottom: -30px;"/>
        </q-list><br>
      </q-list>

      <q-list>
          <q-item clickable class="containerBtn q-mt-md" >
            <q-item-section avatar>
              <q-icon size="31px" class="q-pl-sm" :name="'img:/icons/biny_icons/history_orders.svg'" />
            </q-item-section>
            <q-item-section class="textMenu" style="margin-left: -14px;">
              История заказов
            </q-item-section>
          </q-item>

          <q-separator class="bottom_line q-ml-sm q-mr-sm q-mt-md" size="0.5px"/>

          <q-item clickable class="q-mt-md containerBtn">
            <q-item-section avatar>
              <q-icon size="31px" class="q-pl-sm" :name="'img:/icons/biny_icons/transportCompany.svg'" />
            </q-item-section>
            <q-item-section class="textMenu" style="margin-left: -14px;">
              Транспортные компании
            </q-item-section>
          </q-item>

          <q-item clickable class="q-mt-md containerBtn">
            <q-item-section avatar>
              <q-icon size="31px" class="q-pl-sm" :name="'img:/icons/biny_icons/directions.svg'" />
            </q-item-section>
            <q-item-section class="textMenu" style="margin-left: -14px;">
              Направления
            </q-item-section>
          </q-item>

          <q-separator class="bottom_line q-ml-sm q-mr-sm q-mt-md" size="0.5px"/>

          <q-item clickable class="q-mt-md containerBtn">
            <q-item-section avatar>
              <q-icon size="31px" class="q-pl-sm" :name="'img:/icons/biny_icons/staff.svg'" />
            </q-item-section>
            <q-item-section class="textMenu" style="margin-left: -14px;">
              Сотрудники
            </q-item-section>
          </q-item>

          <q-item clickable class="q-mt-md containerBtn">
            <q-item-section avatar>
              <q-icon size="31px" class="q-pl-sm" :name="'img:/icons/biny_icons/document_flow.svg'" />
            </q-item-section>
            <q-item-section class="textMenu" style="margin-left: -14px;">
              Документооборот
            </q-item-section>
          </q-item>

          <q-item clickable class="q-mt-md containerBtn">
            <q-item-section avatar>
              <q-icon size="31px" class="q-pl-sm" :name="'img:/icons/biny_icons/invoices.svg'" />
            </q-item-section>
            <q-item-section class="textMenu" style="margin-left: -14px;">
              Счет-фактуры
            </q-item-section>
          </q-item>

          <q-item clickable class="q-mt-md containerBtn">
            <q-item-section avatar>
              <q-icon size="31px" class="q-pl-sm" :name="'img:/icons/biny_icons/analytics.svg'" />
            </q-item-section>
            <q-item-section class="textMenu" style="margin-left: -14px;">
              Аналитика
            </q-item-section>
          </q-item>

          <q-item clickable class="q-mt-md containerBtn">
            <q-item-section avatar>
              <q-icon size="31px" class="q-pl-sm" :name="'img:/icons/biny_icons/support.svg'" />
            </q-item-section>
            <q-item-section class="textMenu" style="margin-left: -14px;">
              Поддержка
            </q-item-section>
          </q-item>
      </q-list>
     </q-scroll-area>

      <q-footer style="background-color: #252729; margin-bottom: -100px;" class="q-mr-md">
            <q-item>
              <q-item-section avatar>
                <q-icon
                  name="img:/icons/biny_icons/wallet.svg"
                  size="lg"
                />
              </q-item-section>
              <q-item-section style="margin-left: -10px; border-radius: 15px; font-size: px;"> 450 000 ₸ </q-item-section>
              <q-item-section
                ><q-btn
                  style="width: 70px; border-radius: 10px;"
                  class="white-box bg-white text-black textBalanse q-ml-xl"
                  no-caps
                  label="Баланс"
              /></q-item-section>
            </q-item>
            <q-item>
              <q-item-section avatar>
                <q-icon
                  name="img:/icons/biny_icons/profile.svg"
                  size="lg"
                />
              </q-item-section>
              <q-item-section style="margin-left: -10px;"> ТОО "GORILLA ASIA" </q-item-section>
              <q-item-section
                ><q-btn icon="img:/icons/biny_icons/exit.svg" style="align-items: flex-end; margin-left: 80px;"
              /></q-item-section>
            </q-item>
      </q-footer>
    </q-drawer>


    </q-layout>
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue'
export default defineComponent({
  name: 'MainLayout',


  setup () {
    const leftDrawerOpen = ref(false)
    const dropdownOpen = ref(false)
    const miniState = ref(false)

    return {
      leftDrawerOpen, dropdownOpen, miniState,
      drawer: ref(false),

      showDropdown() {
        dropdownOpen.value = !dropdownOpen.value
        miniState.value = miniState.value
      },

      model: ref(null),
    }
  }
})
</script>

<style>
  *{
    font-family: Inter;
  }

  .q-list .q-item {
    min-height: 0;
    padding: 0;
  }

  .line {
    width: 23.98486328125px;
    height: 4.90673828125px;
  }

  .textMenu {
  font-size: 16px;
  font-weight: 500;
  line-height: 19px;
  letter-spacing: 0.02em;
  text-align: left;
  color: white;
  border-radius: 10px;
  }

  .bottom_line {
    background-color: rgb(154, 149, 149);
  }

  span .block {
    padding-left: 2px;
  }

  .q-drawer__content {
    border-top-right-radius: 12px;
    border-bottom-right-radius: 12px;
  }

  .menu_icon {
    width: 18.416667938232422px;
    height: 13px;
  }

  .q-menu {
    background-color: #252729; box-shadow: none; border: none;
  }

  .q-btn::before {
    box-shadow: none;
  }

  .q-btn--standard {
    padding: 0;
  }

  .dropDownText {
    font-family: Inter;
    font-size: 15px;
    font-weight: 300;
    line-height: 19px;
    letter-spacing: 0.02em;
    color: #ffffff;
  }

  ::-webkit-scrollbar {
    width: 0.5em;
    background-color: transparent;
  }
  ::-webkit-scrollbar-thumb {
    background-color: transparent;
  }

  .numberDropDownText {
    background: rgba(250, 250, 250, 0.1);
    border-radius: 10px;
    align-items: center;
    justify-content: center;
    padding: 3px 6px;
  }

  .q-item .q-icon {
    margin-left: -8px;
  }

  .q-list .q-btn .on-left {
    margin-left: -2px;
  }

  .historyBtn {
    margin-left: 10px;
    padding-left: 5px;
  }

 .q-btn-dropdown--simple * + .q-btn-dropdown__arrow {
    margin-left: 78px;
}

  .containerBtn {
    margin-left: 12px;
    margin-right: 12px;
    border-radius: 10px;
  }

  .fit {
    height: 120% !important;
  }

  .q-toolbar {
    min-height: 0;
    padding-left: 0;
  }

  .textBalanse {
    font-size: 14px;
    font-weight: 500;
  }
</style>
