<template>
    <div class="nav">
        <div class="left">
            <div class="title">
                <nuxt-link to="/">小柒博客</nuxt-link>
            </div>
            <div class="item">
                <ul class="first">
                    <li v-for="(item, index) in nav" :key="index">
                        <div v-if="item.type">
                            <router-link
                                :to="'/category' + item.path + '.html'"
                                >{{ item.name }}</router-link
                            >
                        </div>

                        <div v-if="!item.type">
                            <router-link :to="'/page' + item.path + '.html'">{{
                                item.name
                            }}</router-link>
                        </div>

                        <ul class="second">
                            <li
                                v-for="(list, index) in item.children"
                                :key="index"
                            >
                                <div v-if="item.type">
                                    <router-link
                                        :to="'/category' + list.path + '.html'"
                                        >{{ list.name }}</router-link
                                    >
                                </div>
                                <div v-if="!item.type">
                                    <router-link
                                        :to="'/page' + list.path + '.html'"
                                        >{{ list.name }}</router-link
                                    >
                                </div>
                            </li>
                        </ul>
                    </li>
                </ul>
            </div>
        </div>
        <div class="right">
            <div class="dn" @click="changeDayNight">
                <div class="day">
                    <svg
                        id="icon-_moon"
                        viewBox="0 0 1024 1024"
                        v-if="!this.day"
                    >
                        <path
                            d="M512 512m-512 0a512 512 0 1 0 1024 0 512 512 0 1 0-1024 0Z"
                            fill="#323232"
                        ></path>
                        <path
                            d="M512 512m-407.005867 0a407.005867 407.005867 0 1 0 814.011734 0 407.005867 407.005867 0 1 0-814.011734 0Z"
                            fill="#494A4A"
                        ></path>
                        <path
                            d="M748.1344 633.9584c0-1.143467 0.085333-2.286933 0.085333-3.413333a69.512533 69.512533 0 0 0-8.823466-33.979734q-1.058133-1.911467-2.2528-3.7376l-0.187734-0.3072a70.485333 70.485333 0 0 0-5.2736-7.099733l-0.238933-0.273067q-1.3312-1.536-2.730667-3.003733l-0.3072-0.324267a70.894933 70.894933 0 0 0-6.417066-5.819733l-0.5632-0.443733q-1.467733-1.160533-3.003734-2.235734l-0.494933-0.341333q-1.706667-1.2288-3.6352-2.3552l-0.256-0.136533q-1.706667-0.989867-3.413333-1.8944l-0.887467-0.4608q-1.604267-0.802133-3.242667-1.536l-0.6144-0.273067q-1.928533-0.836267-3.9424-1.553067l-0.8192-0.273066a54.8864 54.8864 0 0 0-3.242666-1.024l-1.143467-0.324267a85.248 85.248 0 0 0-3.601067-0.887467l-0.546133-0.119466a67.345067 67.345067 0 0 0-4.1984-0.733867l-1.143467-0.136533q-1.706667-0.2048-3.2768-0.341334l-1.245866-0.1024a74.786133 74.786133 0 0 0-4.386134-0.1536 69.8368 69.8368 0 0 0-20.48 3.037867 104.106667 104.106667 0 0 0-12.1344-11.076267 258.696533 258.696533 0 0 0-449.9456-248.763733 183.1424 183.1424 0 0 1 106.939734-34.2528c5.12 0 10.24 0.221867 15.36 0.631467a183.125333 183.125333 0 0 1 50.5344 11.52h0.170666q3.874133 1.501867 7.68 3.157333l0.256 0.1024 7.441067 3.413333 0.273067 0.136534q3.669333 1.826133 7.253333 3.805866l0.221867 0.119467q3.618133 2.013867 7.133866 4.164267a184.610133 184.610133 0 0 1 26.760534 20.036266h0.085333q2.986667 2.696533 5.870933 5.5296l0.324267 0.3072q2.781867 2.7648 5.461333 5.632l0.443734 0.477867q2.6112 2.833067 5.12 5.768533l0.494933 0.580267q2.4576 2.9184 4.795733 5.956267l0.494934 0.648533q2.321067 3.037867 4.522666 6.178133l0.426667 0.6144q2.2016 3.1744 4.283733 6.4512l0.324267 0.529067q2.116267 3.413333 4.078933 6.826667l0.170667 0.3072c1.553067 2.7136 3.0208 5.495467 4.437333 8.2944a56.149333 56.149333 0 0 0-12.578133 2.304 82.824533 82.824533 0 0 0-134.007467 18.039466 42.530133 42.530133 0 0 0-53.009066 41.079467 104.277333 104.277333 0 0 0-42.2912 80.110933 13.653333 13.653333 0 0 0 0 1.4336v0.426667c0 0.136533 0.1024 0.682667 0.187733 1.024s0 0.3072 0.1024 0.4608 0.2048 0.733867 0.324267 1.092267l0.1024 0.3072a15.36 15.36 0 0 0 0.580266 1.416533l0.1024 0.187733a16.520533 16.520533 0 0 0 0.648534 1.211734l0.221866 0.3584c0.221867 0.3584 0.4608 0.733867 0.7168 1.092266l0.221867 0.3072a26.333867 26.333867 0 0 0 2.338133 2.798934l0.119467 0.119466q0.6144 0.631467 1.297067 1.262934l0.2048 0.187733q0.7168 0.648533 1.501866 1.297067 1.706667 1.416533 3.720534 2.781866c0.6656 0.4608 1.348267 0.904533 2.065066 1.348267 26.914133 16.7936 87.995733 28.535467 159.044267 28.535467 19.3536 0 37.956267-0.8704 55.3472-2.474667l-0.494933 0.750933-0.426667 0.6144q-2.2016 3.140267-4.539733 6.178134l-0.477867 0.631466q-2.338133 3.037867-4.795733 5.956267l-0.494934 0.580267q-2.491733 2.935467-5.12 5.7856l-0.443733 0.477866q-2.679467 2.884267-5.461333 5.649067l-0.3072 0.290133q-2.884267 2.833067-5.870934 5.546667a184.8832 184.8832 0 0 1-26.7776 20.036267q-3.515733 2.167467-7.150933 4.181333l-0.187733 0.1024q-3.584 1.979733-7.2704 3.805867l-0.256 0.136533q-3.6864 1.826133-7.458134 3.413333l-0.238933 0.1024q-3.805867 1.706667-7.68 3.157334h-0.136533a183.057067 183.057067 0 0 1-50.551467 11.52c-5.12 0.4096-10.24 0.631467-15.36 0.631466a183.159467 183.159467 0 0 1-106.939733-34.2528 258.5088 258.5088 0 0 0 180.138666 107.093334 109.550933 109.550933 0 0 0-3.259733 26.453333 16.520533 16.520533 0 0 0 0.1024 1.706667v0.529066c0 0.170667 0.136533 0.853333 0.221867 1.262934l0.136533 0.5632 0.392533 1.365333 0.136534 0.4096a13.892267 13.892267 0 0 0 0.733866 1.706667l0.119467 0.238933c0.238933 0.512 0.512 1.006933 0.802133 1.501867l0.273067 0.443733q0.4096 0.682667 0.887467 1.365333l0.273066 0.375467a33.0752 33.0752 0 0 0 2.9184 3.413333l0.1536 0.1536 1.5872 1.553067 0.273067 0.256 1.8432 1.621333q2.116267 1.706667 4.625067 3.413334l2.56 1.706666c33.467733 20.8896 109.431467 35.4816 197.802666 35.4816 119.330133 0 216.046933-26.606933 216.046934-59.409066a131.413333 131.413333 0 0 0-56.285867-102.058667z"
                            fill="#323232"
                        ></path>
                        <path
                            d="M573.8496 401.8176v-2.781867a56.200533 56.200533 0 0 0-72.6016-53.725866 82.824533 82.824533 0 0 0-134.007467 18.039466 42.530133 42.530133 0 0 0-53.009066 41.079467 104.277333 104.277333 0 0 0-42.257067 80.0768c0 26.385067 77.7728 47.786667 173.7216 47.786667s173.7216-21.384533 173.7216-47.786667a105.659733 105.659733 0 0 0-45.568-82.688z"
                            fill="#CDCCCA"
                        ></path>
                        <path
                            d="M293.768533 506.2656a104.277333 104.277333 0 0 1 42.2912-80.110933 42.530133 42.530133 0 0 1 53.009067-41.079467 82.807467 82.807467 0 0 1 134.007467-18.039467 56.32 56.32 0 0 1 43.758933 4.642134 56.2176 56.2176 0 0 0-65.518933-26.4192 82.824533 82.824533 0 0 0-134.007467 18.039466 42.530133 42.530133 0 0 0-53.009067 41.079467 104.277333 104.277333 0 0 0-42.325333 80.128c0 8.413867 7.936 16.3328 21.845333 23.210667a13.294933 13.294933 0 0 1-0.0512-1.450667z"
                            fill="#E8E9EC"
                        ></path>
                        <path
                            d="M453.4784 166.912a258.338133 258.338133 0 0 0-210.944 108.919467 183.995733 183.995733 0 1 1 0 299.451733 258.6624 258.6624 0 1 0 210.944-408.388267z"
                            fill="#DDAE2A"
                        ></path>
                        <path
                            d="M364.834133 608.9216q7.594667 0.631467 15.36 0.648533a183.995733 183.995733 0 0 0 0-367.9744q-7.748267 0-15.36 0.631467a183.995733 183.995733 0 0 1 0 366.6944z"
                            fill="#EDC849"
                        ></path>
                        <path
                            d="M794.7776 605.969067c0-1.143467 0.085333-2.286933 0.085333-3.413334a69.973333 69.973333 0 0 0-90.299733-66.833066 102.997333 102.997333 0 0 0-166.656 22.4256 52.906667 52.906667 0 0 0-65.928533 51.0976 129.706667 129.706667 0 0 0-52.599467 99.6352c0 32.8192 96.733867 59.409067 216.046933 59.409066s216.046933-26.606933 216.046934-59.409066a131.413333 131.413333 0 0 0-56.695467-102.912z"
                            fill="#CDCCCA"
                        ></path>
                        <path
                            d="M446.481067 735.914667a129.706667 129.706667 0 0 1 52.599466-99.6352 52.906667 52.906667 0 0 1 65.928534-51.080534 102.997333 102.997333 0 0 1 166.6048-22.442666 69.973333 69.973333 0 0 1 54.408533 5.7856 69.973333 69.973333 0 0 0-81.476267-32.853334 102.997333 102.997333 0 0 0-166.656 22.4256 52.906667 52.906667 0 0 0-65.928533 51.0976 129.706667 129.706667 0 0 0-52.599467 99.6352c0 10.478933 9.864533 20.309333 27.170134 28.859734a17.408 17.408 0 0 1-0.0512-1.792z"
                            fill="#E8E9EC"
                        ></path>
                    </svg>
                    <svg id="icon-sun" viewBox="0 0 1024 1024" v-else>
                        <path
                            d="M511.99976 511.99976m-511.99976 0a511.99976 511.99976 0 1 0 1023.99952 0 511.99976 511.99976 0 1 0-1023.99952 0Z"
                            fill="#91D2F2"
                        ></path>
                        <path
                            d="M144.623932 868.455593C237.679889 964.327548 367.831828 1023.99952 511.99976 1023.99952c269.983873 0 490.99977-209.007902 510.455761-474.031778C956.991551 535.703749 887.559584 527.999753 815.623618 527.999753c-309.535855 0-572.895731 142.055933-670.999686 340.45584z"
                            fill="#198058"
                        ></path>
                        <path
                            d="M979.623541 575.99973c-351.319835 0-647.791696 155.655927-741.279653 368.639827A509.359761 509.359761 0 0 0 511.99976 1023.99952c260.839878 0 475.967777-195.111909 507.799762-447.31979a1194.34344 1194.34344 0 0 0-40.175981-0.68z"
                            fill="#1E9969"
                        ></path>
                        <path
                            d="M69.711967 769.831639C158.503926 921.815568 323.271848 1023.99952 511.99976 1023.99952a509.455761 509.455761 0 0 0 269.631874-76.783964C657.111692 828.375612 464.271782 751.999648 247.623884 751.999648c-61.575971 0-121.183943 6.271997-177.911917 17.831991z"
                            fill="#6AA33A"
                        ></path>
                        <path
                            d="M487.887771 1023.39152c-86.543959-122.151943-236.911889-214.679899-417.591804-252.543881 85.11996 144.919932 239.415888 244.279885 417.591804 252.543881z"
                            fill="#95E652"
                        ></path>
                        <path
                            d="M394.159815 167.999921l-45.255979 45.255979L303.647858 167.999921l45.255978-45.255979zM394.159815 503.999764l-45.255979 45.255979L303.655858 503.999764l45.247978-45.247979z"
                            fill="#FFF8E6"
                        ></path>
                        <path
                            d="M180.879915 290.719864l45.247979 45.247979-45.255979 45.255978-45.255979-45.255978zM516.903758 290.719864l45.247978 45.247979-45.247978 45.247978-45.247979-45.247978z"
                            fill="#FFF8E6"
                        ></path>
                        <path
                            d="M198.087907 185.207913h63.99997v63.99997h-63.99997zM435.671796 422.791802h63.99997v63.99997h-63.99997z"
                            fill="#FFF8E6"
                        ></path>
                        <path
                            d="M198.087907 422.791802h63.99997v63.99997h-63.99997zM435.671796 185.207913h63.99997v63.99997h-63.99997z"
                            fill="#FFF8E6"
                        ></path>
                        <path
                            d="M348.879836 335.999843m-183.999913 0a183.999914 183.999914 0 1 0 367.999827 0 183.999914 183.999914 0 1 0-367.999827 0Z"
                            fill="#FFEAB3"
                        ></path>
                        <path
                            d="M348.879836 335.999843m-159.999925 0a159.999925 159.999925 0 1 0 319.99985 0 159.999925 159.999925 0 1 0-319.99985 0Z"
                            fill="#FFDC80"
                        ></path>
                    </svg>
                </div>
                <div class="night">
                    <svg id="icon-sun" viewBox="0 0 1024 1024">
                        <path
                            d="M511.99976 511.99976m-511.99976 0a511.99976 511.99976 0 1 0 1023.99952 0 511.99976 511.99976 0 1 0-1023.99952 0Z"
                            fill="#91D2F2"
                        ></path>
                        <path
                            d="M144.623932 868.455593C237.679889 964.327548 367.831828 1023.99952 511.99976 1023.99952c269.983873 0 490.99977-209.007902 510.455761-474.031778C956.991551 535.703749 887.559584 527.999753 815.623618 527.999753c-309.535855 0-572.895731 142.055933-670.999686 340.45584z"
                            fill="#198058"
                        ></path>
                        <path
                            d="M979.623541 575.99973c-351.319835 0-647.791696 155.655927-741.279653 368.639827A509.359761 509.359761 0 0 0 511.99976 1023.99952c260.839878 0 475.967777-195.111909 507.799762-447.31979a1194.34344 1194.34344 0 0 0-40.175981-0.68z"
                            fill="#1E9969"
                        ></path>
                        <path
                            d="M69.711967 769.831639C158.503926 921.815568 323.271848 1023.99952 511.99976 1023.99952a509.455761 509.455761 0 0 0 269.631874-76.783964C657.111692 828.375612 464.271782 751.999648 247.623884 751.999648c-61.575971 0-121.183943 6.271997-177.911917 17.831991z"
                            fill="#6AA33A"
                        ></path>
                        <path
                            d="M487.887771 1023.39152c-86.543959-122.151943-236.911889-214.679899-417.591804-252.543881 85.11996 144.919932 239.415888 244.279885 417.591804 252.543881z"
                            fill="#95E652"
                        ></path>
                        <path
                            d="M394.159815 167.999921l-45.255979 45.255979L303.647858 167.999921l45.255978-45.255979zM394.159815 503.999764l-45.255979 45.255979L303.655858 503.999764l45.247978-45.247979z"
                            fill="#FFF8E6"
                        ></path>
                        <path
                            d="M180.879915 290.719864l45.247979 45.247979-45.255979 45.255978-45.255979-45.255978zM516.903758 290.719864l45.247978 45.247979-45.247978 45.247978-45.247979-45.247978z"
                            fill="#FFF8E6"
                        ></path>
                        <path
                            d="M198.087907 185.207913h63.99997v63.99997h-63.99997zM435.671796 422.791802h63.99997v63.99997h-63.99997z"
                            fill="#FFF8E6"
                        ></path>
                        <path
                            d="M198.087907 422.791802h63.99997v63.99997h-63.99997zM435.671796 185.207913h63.99997v63.99997h-63.99997z"
                            fill="#FFF8E6"
                        ></path>
                        <path
                            d="M348.879836 335.999843m-183.999913 0a183.999914 183.999914 0 1 0 367.999827 0 183.999914 183.999914 0 1 0-367.999827 0Z"
                            fill="#FFEAB3"
                        ></path>
                        <path
                            d="M348.879836 335.999843m-159.999925 0a159.999925 159.999925 0 1 0 319.99985 0 159.999925 159.999925 0 1 0-319.99985 0Z"
                            fill="#FFDC80"
                        ></path>
                    </svg>
                </div>
            </div>
            <div class="search" @click="search()">
                <svg id="icon-chazhao" viewBox="0 0 1024 1024">
                    <path
                        d="M512 512m-512 0a512 512 0 1 0 1024 0 512 512 0 1 0-1024 0Z"
                        fill="#05D3A1"
                    ></path>
                    <path
                        d="M496.536155 421.022928a50.116402 50.116402 0 1 0 25.058201-43.45679 50.116402 50.116402 0 0 0-25.058201 43.45679z m0 0"
                        fill="#FFFFFF"
                    ></path>
                    <path
                        d="M827.485009 758.518519L687.407407 618.440917a15.35097 15.35097 0 0 0-3.160493-2.37037l-0.677249-0.564374a21.671958 21.671958 0 0 0-5.41799-3.273369l-1.128747-0.677248a33.862434 33.862434 0 0 0-41.989418 7.223985 206.899471 206.899471 0 0 1-156.10582 71.111112 206.899471 206.899471 0 1 1 204.190476-172.246914 34.32522 34.32522 0 0 0 67.724868 11.287478 279.477954 279.477954 0 0 0 3.837742-46.165785 276.091711 276.091711 0 1 0-93.347443 206.560847l117.615521 117.61552a34.280071 34.280071 0 0 0 48.536155-48.42328z"
                        fill="#FFFFFF"
                    ></path>
                </svg>
            </div>
        </div>
        <div :class="'changeDay ' + bgclass" v-show="animation">
            <div class="main mode-sky">
                <div
                    :class="'sunlight ' + skyClass"
                    :style="style"
                    v-show="day"
                ></div>
                <div
                    :class="'moon ' + skyClass"
                    :style="style"
                    v-show="!day"
                ></div>
            </div>
        </div>
        <Search v-if="isSearch" @close="search()" />
    </div>
</template>

<script>
let bg = ["sunlight", "moon"];
import Search from "@/components/Search/Index";
export default {
    name: "Nav",
    data() {
        return {
            day: null, // 是否为白天 true 白天 false 黑夜
            animation: false, // 是否显示动画
            style: null, // 旋转样式
            bgclass: null, // 背景样式
            num: 0, // 点击次数
            skyClass: null, // 太阳跟月亮的类名
            nav: null, // 导航数据
            isSearch: false,
        };
    },
    created() {
        this.getDark();
    },
    mounted() {
        this.getNav();
    },
    methods: {
        search() {
            this.isSearch = !this.isSearch;
            if (this.isSearch) {
                document.body.style.overflow = "hidden";
            } else {
                document.body.style.overflow = "auto";
            }
        },
        // 夜间模式
        changeDayNight() {
            document.body.style.overflow = "hidden";
            this.num++;
            this.day = !this.day;
            this.$store.commit("setSetting", true);
            this.$store.commit("setDark", this.day);
            this.animation = !this.animation;
            var angle = 360;
            angle = angle * this.num;
            if (process.client) {
                if (!this.day) {
                    document.getElementsByTagName("body")[0].className =
                        "light";
                } else {
                    document.getElementsByTagName("body")[0].className = "dark";
                }
            }
            var that = this;
            setTimeout(function () {
                that.style = "transform: rotate(" + angle + "deg);";
            }, 100);
            setTimeout(function () {
                if (that.bgclass == "sunlight") {
                    that.bgclass = "moon";
                    that.skyClass = "skyMoon";
                } else {
                    that.bgclass = "sunlight";
                    that.skyClass = "skySunlight";
                }
            }, 1000);
            setTimeout(function () {
                that.animation = !that.animation;
                document.body.style.overflow = "auto";
            }, 2500);
            if (process.client) {
                window.localStorage.setItem("Dark", this.day);
            }
        },

        // 请求导航
        getNav() {
            this.$api.index.getNav().then((res) => {
                this.nav = res.data;
            });
        },
        getDark() {
            this.$api.system.getDark().then((res) => {
                var isSetting, DarkIs;
                if (process.client) {
                    isSetting = window.localStorage.getItem("isSetting");
                    isSetting = JSON.parse(isSetting);
                    DarkIs = window.localStorage.getItem("Dark");
                }
                if (isSetting) {
                    this.day = JSON.parse(DarkIs);
                    this.$store.commit("setDark", this.day);
                    if (process.client) {
                        if (!this.$store.state.isDark) {
                            document.getElementsByTagName("body")[0].className =
                                "light";
                        } else {
                            document.getElementsByTagName("body")[0].className =
                                "dark";
                        }
                    }
                    if (!this.day) {
                        this.bgclass = bg[0];
                        this.skyClass = "skySunlight";
                    } else {
                        this.bgclass = bg[1];
                        this.skyClass = "skyMoon";
                    }
                } else {
                    if (process.client) {
                        window.localStorage.setItem("Dark", !res.data);
                    }
                    this.day = !res.data;
                    this.$store.commit("setDark", this.day);
                    if (!this.day) {
                        this.bgclass = bg[0];
                        this.skyClass = "skySunlight";
                    } else {
                        this.bgclass = bg[1];
                        this.skyClass = "skyMoon";
                    }
                }
            });
        },
    },
    components: {
        Search,
    },
};
</script>

<style scoped>
a {
    color: #fff;
    font-size: 24px;
    font-weight: 700;
}

.nav {
    width: 1680px !important;
    height: 35px !important;
    margin: 0 auto;
    margin-top: 8px;
    color: #fff;
}

.nav .left {
    display: flex;
    height: 100%;
}

.nav .left .title {
    margin-right: 15px;
}

.nav .left .item .first {
    display: flex;
    align-items: center;
    height: 100%;
}

.nav .left .item .first > li {
    position: relative;
    height: 100%;
    line-height: 2.3;
    padding: 0 10px;
}

.nav .left .item .first li a {
    display: inline-block;
    width: 100%;
    height: 100%;
    font-size: 16px;
}

.nav .left .item .first li > ul {
    display: none;
    position: absolute;
    white-space: nowrap;
    box-shadow: 0 4px 12px 0 rgb(7 17 27 / 10%);
    transform: translate(-15%, 0);
    margin-top: -1px;
}

.nav .left .item .first li:hover .second {
    display: block;
}

.second a {
    padding: 10px 15px;
    background-color: #373b3e;
}

.nav .right {
    display: flex;
    justify-content: center;
    align-items: center;
}

.nav .right > div {
    width: 32px;
    height: 32px;
    cursor: pointer;
}

.nav .right > div:first-child {
    margin-right: 5px;
}

.nav .right > div:last-child {
    margin-left: 5px;
}

.nav .right .night {
    display: none;
}

.changeDay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}

.changeDay .main > div {
    z-index: 1999999999;
    position: fixed;
    left: -50%;
    top: -50%;
    width: 200%;
    height: 200%;
    transform-origin: center bottom;
    transition: 2s cubic-bezier(0.7, 0, 0, 1) all;
}

.mode-sky {
    position: fixed;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
    z-index: 999999;
    opacity: 0;
    transition: 2s ease all;
}

.sunlight .mode-sky {
    opacity: 1;
    background: linear-gradient(#feb8b0, #fef9db);
}

.moon .mode-sky {
    opacity: 1;
    background: linear-gradient(#4c3f6d, #6c62bb, #93b1ed);
}

.changeDay .main > .skySunlight::after {
    position: absolute;
    left: 35%;
    top: 40%;
    width: 150px;
    height: 150px;
    border-radius: 50%;
    content: "";
    background: #f1c40f;
    box-shadow: 0px 0px 10px 10px #f39c12, inset 0px 0px 1px 1px #f39c12;
    z-index: 9999999;
}

.changeDay .main > .skyMoon::after {
    position: absolute;
    left: 35%;
    top: 40%;
    width: 150px;
    height: 150px;
    border-radius: 50%;
    content: "";
    background: linear-gradient(#fefefe, #fffbe8);
    box-shadow: 0px 0px 10px 10px rgb(255, 255, 255, 0.5),
        inset 0px 0px 1px 1px rgb(255, 255, 255, 0.5);
    z-index: 9999999;
}
</style>