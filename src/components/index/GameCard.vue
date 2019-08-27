<template>
  <div class="card" id="gameCard">
    <div v-for="(item, key) in listData" :key="key">
      <div class="card-header" id="gameHeader">
        <h2 class="mb-0">
          <button class="btn btn-link" type="button" data-toggle="collapse" :data-target="['#collapse'+ key]">
            <!-- {{ league }} -->
            {{ item.cell}}
          </button>
        </h2>
      </div>
      <div :id="['collapse'+ key]" class="collapse show" data-parent="#accordion">
        <div v-for="(item, key) in listData" :key="key">
            <div class="card-body p-0" id="gameList">

                <!-- 一場比賽 info  -->
                <div class="container-fluid">
                  <!-- 比賽 nav  -->
                  <div class="row pl-2 pr-2 bg-success">
                    <div class="col-4 d-flex align-items-center p-0" style="font-size: .9rem;">
                      <span class="flex-grow-1">
                        <!-- {{time}} -->
                        {{item.phone}}
                      </span>
                      <span class="mr-2">
                        <!-- {{lid}} -->
                      </span>
                    </div>
                    <div class="col-4 d-flex flex-column p-0" style="font-size: .7rem;">
                      <div class="d-flex justify-content-around">
                        全場
                      </div>
                      <div class=" d-flex justify-content-around align-items-center">
                        <span>1 X 2</span>
                        <span>讓球</span>
                        <span>大/小</span>
                      </div>
      
                    </div>
                    <div class="col-4 d-flex flex-column p-0" style="font-size: .7rem;">
                      <div class="d-flex justify-content-around">
                        上半場
                      </div>
                      <div class=" d-flex justify-content-around align-items-center">
                        <span class="ml-auto mr-auto">1 X 2</span>
                        <span class="ml-auto mr-auto">讓球</span>
                        <span class="ml-auto mr-auto">大/小</span>
                      </div>
      
                    </div>
      
      
                  </div>
                  <!-- 比賽 nav end -->
                  <!-- Home隊伍 info -->
                  <div class="row pl-2 pr-2">
                    <div class="col-4 d-flex align-items-center p-0" style="font-size: .9rem;">
                      <span>
                        <!-- {{home}} -->
                        {{item.name.first}}
                      </span>
                    </div>
                    <div class="col-4 d-flex justify-content-between p-0 mt-1 mb-1">
      
                      <button type="button" class="col btn btn-outline-secondary mr-1">
                        <span>
                          <!-- 全場 1X2 主隊 -->
                          <!-- {{o.[0].1x2.h}} -->
                        </span>
                      </button>
                      <button type="button"
                        class="col btn btn-outline-secondary mr-1 d-flex flex-column align-items-center justify-content-center">
                        <span>
                          <!-- 全場 讓球 主隊 -->
                          <!-- {{o.[0].ah.strong}} {{o.[0].ah.ratio}} -->
                        </span>
                        <span>
                          <!-- {{o.[0].ah.h}} -->
                        </span>
      
      
                      </button>
                      <button type="button"
                        class="col btn btn-outline-secondary mr-1 d-flex flex-column align-items-center justify-content-center">
                        <span>
                          <!-- 全場 大/小 主隊 -->
                          <!-- O {{o.[0].ou.o}} -->
                        </span>
      
                      </button>
      
                    </div>
                    <div class="col-4 d-flex justify-content-between p-0 mt-1 mb-1">
      
                      <button type="button" class="col btn btn-outline-secondary mr-1">
                        <span>
                          <!-- 上半場 1X2 主隊 -->
                          <!-- {{o.[0].1x21st.h}} -->
                        </span>
                      </button>
                      <button type="button"
                        class="col btn btn-outline-secondary mr-1 d-flex flex-column align-items-center justify-content-center">
                        <span>
                          <!-- 上半場 1X2 主隊 -->
                          <!-- {{o.[0].ah1st.strong}} {{o.[0].ah1st.ratio}}                         -->
                        </span>
                        <span>
                          <!-- {{o.[0].ah1st.h}} -->
                        </span>
      
                      </button>
                      <button type="button"
                        class="col btn btn-outline-secondary d-flex flex-column align-items-center justify-content-center">
                        <span>
                          <!-- 上半場 大/小 主隊 -->
                          <!-- O {{o.[0].ou1st.o}} -->
                        </span>
      
      
                      </button>
      
                    </div>
      
                  </div>
                  <!-- Home隊伍 info end -->
                  <!-- Away隊伍 info -->
                  <div class="row pl-2 pr-2">
                    <div class="col-4 d-flex align-items-center p-0" style="font-size: .9rem;">
                      <span>
                        <!-- {{away}} -->
                        {{item.name.last}}
                      </span>
                    </div>
                    <div class="col-4 d-flex justify-content-between p-0 mt-1 mb-1">
      
                      <button type="button" class="col btn btn-outline-secondary mr-1">
                        <span>
                          <!-- 全場 1X2 客隊 -->
                          <!-- {{o.[0].1x2.a}} -->
                        </span>
                      </button>
                      <button type="button"
                        class="col btn btn-outline-secondary mr-1 d-flex flex-column align-items-center justify-content-center">
                        <span>
                          <!-- 全場 讓球 客隊 -->
                          <!-- {{o.[0].ah.a}} -->
                        </span>
      
      
                      </button>
                      <button type="button"
                        class="col btn btn-outline-secondary mr-1 d-flex flex-column align-items-center justify-content-center">
                        <span>
                          <!-- 全場 大/小 客隊 -->
                          <!-- U {{o.[0].ou.u}} -->
                        </span>
                      </button>
      
                    </div>
                    <div class="col-4 d-flex justify-content-between p-0 mt-1 mb-1">
      
                      <button type="button" class="col btn btn-outline-secondary mr-1">
                        <span>
                          <!-- 上半場 1X2 客隊 -->
                          <!-- {{o.[0].1x21st.a}} -->
                        </span>
                      </button>
                      <button type="button"
                        class="col btn btn-outline-secondary mr-1 d-flex flex-column align-items-center justify-content-center">
                        <span>
                          <!-- 上半場 1X2 客隊 -->
                          <!-- {{o.[0].ah1st.strong}} {{o.[0].ah1st.ratio}}   -->
                          <!-- {{o.[0].ah1st.a}} -->
                        </span>
      
      
                      </button>
                      <button type="button"
                        class="col btn btn-outline-secondary d-flex flex-column align-items-center justify-content-center">
                        <span>
                          <!-- 上半場 大/小 客隊 -->
                          <!-- U {{o.[0].ou1st.u}} -->
                        </span>
      
                      </button>
      
                    </div>
      
                  </div>
                  <!-- Away隊伍 info end -->
                  <!-- 和局  -->
                  <div class="row pl-2 pr-2">
                    <div class="col-4 d-flex align-items-center p-0" style="font-size: .9rem;">
                      <span>和局</span>
                    </div>
                    <div class="col-4 d-flex justify-content-between p-0 mt-1 mb-1">
      
                      <button type="button" class="col btn btn-outline-secondary mr-1">
                        <span>
                          <!-- 全場 和局 -->
                          <!-- {{o.[0].1x2.d}} -->
                        </span>
                      </button>
      
                    </div>
                    <div class="col-4 d-flex justify-content-between p-0 mt-1 mb-1">
      
                      <button type="button" class="col btn btn-outline-secondary">
                        <span>
                          <!-- 上半場 和局 -->
                          <!-- {{o.[0].1x21st.d}} -->
                        </span>
                      </button>
      
                    </div>
      
                  </div>
                  <!-- 和局 end -->
                  <!-- 現有更高賠率  -->
                  <div class="row pl-2 pr-2">
                    <div class="col d-flex align-items-center p-0 mt-1 mb-1" style="font-size: .9rem;">
                      <button type="button" class="col btn btn-outline-secondary">
                        <span>現有更高賠率</span>
                      </button>
                    </div>
      
      
                  </div>
                  <!-- 現有更高賠率 end -->
      
                </div>
      
                <!-- 一場比賽 info end -->
      
              </div>

        </div>
       

      </div>
    </div>
  </div>


</template>

<script>
  export default {
    name: 'gameCard',
    data() {
      return {
        listData: [],
      }
    },
    components: {

    },
    methods: {
      getData: function () {
        let self = this;
        let api = 'https://randomuser.me/api/?results=5';
        self.axios.get(api).then((response) => {
          self.listData = response.data.results;
          console.log(self.listData);
        })
      }
    },

    mounted() {
      this.getData()
    }

  }

</script>
