<template>
  <div class="dashboard-container">
    <component :is="currentRole" />
  </div>
</template>
   <div data-v-55eb21f8="" class="el-tabs el-tabs--top el-tabs--border-card" style="margin-top: 15px;">
    <div class="el-tabs__header is-top">
      <div class="el-tabs__nav-wrap is-top">
        <div class="el-tabs__nav-scroll">
          <div role="tablist" class="el-tabs__nav is-top" style="transform: translateX(0px);">
            <div id="tab-CN" aria-controls="pane-CN" role="tab" tabindex="0" class="el-tabs__item is-top is-active"
              aria-selected="true">China</div>
            <div id="tab-US" aria-controls="pane-US" role="tab" tabindex="-1" class="el-tabs__item is-top">USA</div>
            <div id="tab-JP" aria-controls="pane-JP" role="tab" tabindex="-1" class="el-tabs__item is-top">Japan</div>
            <div id="tab-EU" aria-controls="pane-EU" role="tab" tabindex="-1" class="el-tabs__item is-top">Eurozone
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="el-tabs__content">
      <div data-v-55eb21f8="" role="tabpanel" id="pane-CN" aria-labelledby="tab-CN" class="el-tab-pane" style="">
        <div data-v-55eb21f8=""
          class="el-table el-table--fit el-table--border el-table--enable-row-hover el-table--enable-row-transition el-table--medium"
          style="width: 100%;">
          <div class="hidden-columns">
            <div element-loading-text="请给我点时间！"></div>
            <div></div>
            <div></div>
            <div></div>
            <div></div>
            <div></div>
            <div></div>
          </div>
          <div class="el-table__header-wrapper">
            <table cellspacing="0" cellpadding="0" border="0" class="el-table__header" style="width: 1617px;">
              <colgroup>
                <col name="el-table_2_column_4" width="65">
                <col name="el-table_2_column_5" width="180">
                <col name="el-table_2_column_6" width="937">
                <col name="el-table_2_column_7" width="110">
                <col name="el-table_2_column_8" width="120">
                <col name="el-table_2_column_9" width="95">
                <col name="el-table_2_column_10" width="110">
                <col name="gutter" width="0">
              </colgroup>
              <thead class="has-gutter">
                <tr class="">
                  <th colspan="1" rowspan="1" class="el-table_2_column_4  is-center   is-leaf">
                    <div class="cell">ID</div>
                  </th>
                  <th colspan="1" rowspan="1" class="el-table_2_column_5  is-center   is-leaf">
                    <div class="cell">Date</div>
                  </th>
                  <th colspan="1" rowspan="1" class="el-table_2_column_6     is-leaf">
                    <div class="cell">Title</div>
                  </th>
                  <th colspan="1" rowspan="1" class="el-table_2_column_7  is-center   is-leaf">
                    <div class="cell">Author</div>
                  </th>
                  <th colspan="1" rowspan="1" class="el-table_2_column_8     is-leaf">
                    <div class="cell">Importance</div>
                  </th>
                  <th colspan="1" rowspan="1" class="el-table_2_column_9  is-center   is-leaf">
                    <div class="cell">Readings</div>
                  </th>
                  <th colspan="1" rowspan="1" class="el-table_2_column_10   status-col  is-leaf">
                    <div class="cell">Status</div>
                  </th>
                  <th class="gutter" style="width: 0px; display: none;"></th>
                </tr>
              </thead>
            </table>
          </div>
          <div class="el-table__body-wrapper is-scrolling-none">
            <table cellspacing="0" cellpadding="0" border="0" class="el-table__body" style="width: 1617px;">
              <colgroup>
                <col name="el-table_2_column_4" width="65">
                <col name="el-table_2_column_5" width="180">
                <col name="el-table_2_column_6" width="937">
                <col name="el-table_2_column_7" width="110">
                <col name="el-table_2_column_8" width="120">
                <col name="el-table_2_column_9" width="95">
                <col name="el-table_2_column_10" width="110">
              </colgroup>
              <tbody>
                <tr class="el-table__row">
                  <td rowspan="1" colspan="1" class="el-table_2_column_4 is-center ">
                    <div class="cell"><span>2</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_5 is-center ">
                    <div class="cell"><span>1989-06-25 13:21</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_6  ">
                    <div class="cell"><span>Cupvvp Ecskvniw Kbxj Ovbpaouck Lbrv Uhqyfaxf Tukru Pltezlhsp Ikvora</span>
                      <span class="el-tag el-tag--medium">CN</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_7 is-center ">
                    <div class="cell"><span>Sandra</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_8  ">
                    <div class="cell"><svg data-v-f9f7fefc="" aria-hidden="true" class="svg-icon">
                        <use data-v-f9f7fefc="" xlink:href="#icon-star"></use>
                      </svg><svg data-v-f9f7fefc="" aria-hidden="true" class="svg-icon">
                        <use data-v-f9f7fefc="" xlink:href="#icon-star"></use>
                      </svg></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_9 is-center ">
                    <div class="cell"><span>1083</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_10  status-col">
                    <div class="cell"><span class="el-tag el-tag--success el-tag--medium">
                        published
                      </span></div>
                  </td>
                </tr>
                <tr class="el-table__row">
                  <td rowspan="1" colspan="1" class="el-table_2_column_4 is-center ">
                    <div class="cell"><span>4</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_5 is-center ">
                    <div class="cell"><span>2004-01-06 23:32</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_6  ">
                    <div class="cell"><span>Fxdpydf Rbfzbwjg Fkgbnwifw Vhvrd Vkpdctyqmr Eukclb Ejsubv Raotyg
                        Agkqz</span> <span class="el-tag el-tag--medium">CN</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_7 is-center ">
                    <div class="cell"><span>Paul</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_8  ">
                    <div class="cell"><svg data-v-f9f7fefc="" aria-hidden="true" class="svg-icon">
                        <use data-v-f9f7fefc="" xlink:href="#icon-star"></use>
                      </svg><svg data-v-f9f7fefc="" aria-hidden="true" class="svg-icon">
                        <use data-v-f9f7fefc="" xlink:href="#icon-star"></use>
                      </svg><svg data-v-f9f7fefc="" aria-hidden="true" class="svg-icon">
                        <use data-v-f9f7fefc="" xlink:href="#icon-star"></use>
                      </svg></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_9 is-center ">
                    <div class="cell"><span>1271</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_10  status-col">
                    <div class="cell"><span class="el-tag el-tag--success el-tag--medium">
                        published
                      </span></div>
                  </td>
                </tr>
                <tr class="el-table__row">
                  <td rowspan="1" colspan="1" class="el-table_2_column_4 is-center ">
                    <div class="cell"><span>10</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_5 is-center ">
                    <div class="cell"><span>2012-12-10 19:04</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_6  ">
                    <div class="cell"><span>Apcdut Xldirrgo Jlnnfvji Wrjreh Iqsm Psbnk Yiiafiwwa Biuzfnbpp</span> <span
                        class="el-tag el-tag--medium">CN</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_7 is-center ">
                    <div class="cell"><span>Kimberly</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_8  ">
                    <div class="cell"><svg data-v-f9f7fefc="" aria-hidden="true" class="svg-icon">
                        <use data-v-f9f7fefc="" xlink:href="#icon-star"></use>
                      </svg></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_9 is-center ">
                    <div class="cell"><span>828</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_10  status-col">
                    <div class="cell"><span class="el-tag el-tag--success el-tag--medium">
                        published
                      </span></div>
                  </td>
                </tr>
                <tr class="el-table__row">
                  <td rowspan="1" colspan="1" class="el-table_2_column_4 is-center ">
                    <div class="cell"><span>11</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_5 is-center ">
                    <div class="cell"><span>2005-11-18 02:21</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_6  ">
                    <div class="cell"><span>Eoajhdc Rojfwcbjp Zzkhgota Dlhegjzc Dcqdxr Ndmitnwm Jekxyrknzh</span> <span
                        class="el-tag el-tag--medium">CN</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_7 is-center ">
                    <div class="cell"><span>Maria</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_8  ">
                    <div class="cell"><svg data-v-f9f7fefc="" aria-hidden="true" class="svg-icon">
                        <use data-v-f9f7fefc="" xlink:href="#icon-star"></use>
                      </svg></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_9 is-center ">
                    <div class="cell"><span>3437</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_10  status-col">
                    <div class="cell"><span class="el-tag el-tag--danger el-tag--medium">
                        deleted
                      </span></div>
                  </td>
                </tr>
                <tr class="el-table__row">
                  <td rowspan="1" colspan="1" class="el-table_2_column_4 is-center ">
                    <div class="cell"><span>16</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_5 is-center ">
                    <div class="cell"><span>2001-09-08 23:07</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_6  ">
                    <div class="cell"><span>Lcsjixwr Qdilr Yrxcvrzldq Qbmdbelhv Lewsjpb Ubnquxxrv Whvsv Qoox</span>
                      <span class="el-tag el-tag--medium">CN</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_7 is-center ">
                    <div class="cell"><span>Eric</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_8  ">
                    <div class="cell"><svg data-v-f9f7fefc="" aria-hidden="true" class="svg-icon">
                        <use data-v-f9f7fefc="" xlink:href="#icon-star"></use>
                      </svg></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_9 is-center ">
                    <div class="cell"><span>3613</span></div>
                  </td>
                  <td rowspan="1" colspan="1" class="el-table_2_column_10  status-col">
                    <div class="cell"><span class="el-tag el-tag--info el-tag--medium">
                        draft
                      </span></div>
                  </td>
                </tr>
                <!---->
              </tbody>
            </table>
            <!---->
            <!---->
          </div>
          <!---->
          <!---->
          <!---->
          <!---->
          <div class="el-table__column-resize-proxy" style="display: none;"></div>
        </div>
      </div>
      <div data-v-55eb21f8="" role="tabpanel" id="pane-US" aria-labelledby="tab-US" class="el-tab-pane"
        style="display: none;" aria-hidden="true">
        <!---->
      </div>
      <div data-v-55eb21f8="" role="tabpanel" id="pane-JP" aria-labelledby="tab-JP" class="el-tab-pane"
        style="display: none;" aria-hidden="true">
        <!---->
      </div>
      <div data-v-55eb21f8="" role="tabpanel" id="pane-EU" aria-labelledby="tab-EU" class="el-tab-pane"
        style="display: none;" aria-hidden="true">
        <!---->
      </div>
    </div>
  </div>

<script>
import { mapGetters } from 'vuex'
import adminDashboard from './admin'
import editorDashboard from './editor'

export default {
  name: 'Dashboard',
  components: { adminDashboard, editorDashboard },
  data() {
    return {
      currentRole: 'adminDashboard'
    }
  },
  computed: {
    ...mapGetters([
      'roles'
    ])
  },
  created() {
    if (!this.roles.includes('admin')) {
      this.currentRole = 'editorDashboard'
    }
  }
}
</script>
