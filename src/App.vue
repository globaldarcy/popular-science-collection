<template>
    <div id="app">
        <div class="darcy-container">
            <h1 class="darcy-large-title">
                鹤叔医疗科普合集<br /><small>谨以此整理稿为“仙鹤大叔张文鹤”公众号上线献礼<br />（20200322版）</small>
            </h1>
            <p class="darcy-author">灯火阑珊 整理版</p>
            <p class="darcy-desc">整理者按：2019年10月份，一个偶然的机会通过抖音关注了鹤叔，他教我们通过最简单的方式，使用最便宜、易得的药物来解决常见的皮肤问题。不仅告诉我们治疗的方法，还解析了疾病的发病原理，使我们解除了痛苦，甚至治愈了很多久拖不愈的疑难杂症。鹤叔说他做科普一不为名，二不图利，就是希望老百姓多些知识的储备，少些后悔。通过鹤叔的科普，越来越多的人自己在家就解决了原本四处求医都不见好转的皮肤问题。 杏林春满，医者仁心。鹤叔的科普如星星之火，以燎原之势在造福更多的百姓。希望我的整理稿，如一阵清风，带着这星火传递给更多有缘人。 感恩鹤叔的无私科普，感谢壮壮、小柒、桂俊等鹤粉的指导和校对！</p>
            <el-card class="box-card darcy-alert">
                <div class="darcy-alert-title">郑重声明</div>
                科普的意思就是普及知识，让大家了解知识，有问题能早发现、早干预，给大家一个方向。 本资料是我个人根据自己学习鹤叔科普的内容整理而成，仅可作为参考，并不代表一定是鹤叔讲的全部，也不敢说能把鹤叔讲的100%还原。所以大家千万不要把我的笔记当成书，因为它不具有权威性，毕竟从鹤叔口中传到我这里，肯定会有一些我个人的理解和表述成份，难免存在疏漏或错误。 <br /><br /><b>郑重提醒大家，有病找医生确诊，结合鹤叔科普做个参考，不要私自诊治，以免延误病情。</b>
            </el-card>
            <h2 class="darcy-title">{{ infoOneTitle }}</h2>
            <el-collapse class="darcy-content" accordion v-model="activeName">
                <el-collapse-item v-for="(item, index) in infoOne" :key="index" :name="index">
                    <template slot="title">{{ index + 1 }}、{{ item.title }}</template>
                    <div v-html="item.description"></div>
                </el-collapse-item>
            </el-collapse>
            <h2 class="darcy-title">{{ infoTwoTitle }}</h2>
            <div class="darcy-block" v-for="(item, index) in infoTwo" :key="index">
                <h3 class="darcy-sub-title">{{ item.subTitle }}</h3>
                <el-collapse class="darcy-content" accordion>
                    <el-collapse-item v-for="(subItem, subIndex) in item.subList" :key="subIndex" :name="subIndex">
                        <template slot="title">{{ subIndex + 1 }}、{{ subItem.title }}</template>
                        <div v-html="subItem.description"></div>
                    </el-collapse-item>
                </el-collapse>
            </div>
            <h2 class="darcy-title" style="color: #F56C6C">注解：</h2>
            <el-card class="box-card darcy-notes">
                <div class="darcy-text"><b>“坐等还书”</b>：1、“坐（唑）”是一大类，所以叫“唑等“，如达克宁、孚琪、克霉唑，化学名里都有个“唑”;2、“还”是环利软膏，它是合成药类（环丙酮胺）；3、“书”是指丙烯胺类的药物-特比萘芬，别管叫兰美抒、疗霉舒，后面一定有个舒（抒）字，这几种药每个用两三周，轮着换，可以把一些产生耐药性的真菌都杀死（使用顺序唑、环、另一种唑、舒）。</div>
                <div class="darcy-text"><b>十滴水</b>：中药，有清热开窍的功效，原本是用于防中暑的内服药，和藿香正气水一类，但不能用藿香正气水带替十滴水。</div>
                <div class="darcy-text"><b>碘伏</b>：医用碘伏，浓度为1%，市面难买到，一般药店的浓度偏低会降低药效，浓度太高容易烧伤皮肤。</div>
                <div class="darcy-text"><b>开塞露</b>：原本是治疗便秘的外用药，含甘油。</div>
                <div class="darcy-text"><b>乐肤液</b>：哈西奈德溶液，不要买成乐肤杀菌液。</div>
                <div class="darcy-text"><b>黄连素</b>：盐酸小檗碱片。是种从黄连、黄柏和三颗针里面提取的生物碱，人类最早拿它治拉肚子，最新研究发现还能降血脂、降血糖，当然还可以治激素脸。</div>
                <div class="darcy-text"><b>标准黄连素水</b>：5片黄连素（盐酸小檗碱片）磨碎，加入500毫升水中，不需要加热。</div>
                <div class="darcy-text"><b>凡士林</b>：无添加的凡士林，首选贝亲凡士林。</div>
                <div class="darcy-text"><b>甲硝锉、高猛酸钾</b>：都是指的片剂。</div>
                <div class="darcy-text"><b>烫洗</b>：为防止影响治疗治疗效果，对可能细菌、病毒种植的衣物、床品进行处理，方法是将衣物、床品放在大盆里，用开水浇上，等凉后再放洗衣机正常洗涤，频次为一周一次。</div>
                <div class="darcy-text"><b>抗组胺药</b>：是一大类药，有很多种，常见的有扑尔敏、开瑞坦、西替利嗪等，其中扑尔敏最便宜，且在药典中没有明确的不良反应，相对安全，是鹤叔推荐使用的，但吃完后会困，不能开车，如吃完药需开车，可以选择开瑞坦。</div>
            </el-card>
            <div class="darcy-backtop">
                <el-backtop :bottom="50"></el-backtop>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            activeName: 0,
            infoOneTitle: null,
            infoOne: null,
            infoTwoTitle: null,
            infoTwo: null,
        };
    },
    mounted() {
        this.axios.get('http://localhost:3000/comments').then((response) => {
            this.infoOneTitle = response.data[0].title;
            this.infoOne = response.data[0].list;
            this.infoTwoTitle = response.data[1].title;
            this.infoTwo = response.data[1].list;
            console.log(response.data[0].list[0].description);
        });
    },
};
</script>

<style lang="scss">
body {
    margin: 0;
    padding: 0;
}
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
}
.darcy-container {
    position: relative;
    max-width: 768px;
    margin: 0 auto;
    padding: 30px 16px 80px;
    text-align: left;
    font-size: 16px;
    @media screen and (max-width: 768px) {
        font-size: 14px;
    }
    .darcy-content div {
        font-size: 16px;
        @media screen and (max-width: 768px) {
            font-size: 14px;
        }
    }
    .el-collapse-item__header {
        line-height: 1.2;
    }
    .darcy-large-title {
        text-align: center;
        line-height: 1;
        font-size: 24px;
        > small {
            font-size: 0.6em;
        }
    }
    .darcy-title {
        padding-top: 30px;
        font-size: 20px;
        @media screen and (max-width: 768px) {
            font-size: 18px;
        }
    }
    .darcy-author {
        text-align: right;
        color: #409eff;
    }
    .darcy-desc {
        color: #606266;
    }
    .darcy-alert {
        color: #f56c6c;
        border-radius: 10px;
        .darcy-alert-title,
        b {
            font-size: 20px;
            font-weight: bold;
            text-align: center;
            padding-bottom: 10px;
            @media screen and (max-width: 768px) {
                font-size: 18px;
            }
        }
    }
    .darcy-sub-title {
        text-align: center;
        color: #606266;
    }
    .darcy-notes {
        .darcy-text {
            padding: 10px 0;
            > b {
                color: #e6a23c;
            }
        }
    }
    .darcy-backtop {
        width: 100%;
        height: 100%;
    }
}
</style>
