<template>
    <div class="_banner">
        <div class="_big_wrap">
            <div class="_carousel">
                <div class="carousel_items" :class="direction">
                    <template v-for="(post, index) in items">
                            <div :class="['_row-center items_container', {active: divActive == index}]"  :key="index">
                                <figure class="_col _item">
                                    <img :src="post.img" :alt="post.content">
                                    <div class="_wrapper">
                                        <div class="txt-right _banner-content">
                                            <p class="jp-font text_content" v-html="post.content"></p>
                                            <span class="is-block date">{{ post.date }}</span>
                                        </div>
                                    </div>
                                </figure>
                            </div>
                    </template>
                </div>
                <div class="dotted_buttons" v-if="items.length != 1">
                    <a 	href="javascript:;" 
                        v-for="(button, index) in items" 
                        :key="index" 
                        :class="[ (index == divActive ? 'active' : ''), disable == true ? 'disabled' : '' ]"
                        @click="moveCarouselDot(index)"></a>
                </div>
                <div class="move">
                    <a href="javascript:;" :class="['prev', {disabled: divActive == 0}]" @click="move('prev')"></a>
                    <a href="javascript:;" :class="['next', {disabled: divActive == (items.length - 1)}]" @click="move('next')"></a>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            items: [
                {
                    content: `<span>サンプルテキスト</span> <br/><span>サンプル ルテキスト</span> <br/><span>サンプルテキスト</span>`,
                    // content: `商品一覧 ご利用ガイド マイページ`,
                    img: require('../assets/images/banner/banner1.png'),
                    date: '2019.06.19'
                },
                {  
                    content: `<span>サンプルテキスト</span> <br/><span>サンプル ルテキスト</span> <br/><span>サンプルテキスト</span>`,
                    // content: `商品一覧 ご利用ガイド マイページ`,
                    img: require('../assets/images/banner/banner1.png'),
                    date: '2019.06.19'
                },
                {  
                    content: `<span>サンプルテキスト</span> <br/><span>サンプル ルテキスト</span> <br/><span>サンプルテキスト</span>`,
                    // content: `商品一覧 ご利用ガイド マイページ`,
                    img: require('../assets/images/banner/banner1.png'),
                    date: '2019.06.19'
                }
            ],
            lists: 'bc',
            itemsPerRow: 1,
            divActive: 0,
            increment: 0,
            direction: null,
			disable: false,
        }
    },
    methods: {
        move(i) {
            this.direction = i

            if(i == 'next') {
                this.divActive = this.divActive+1
            } else if(i == 'prev') {
                this.divActive = this.divActive-1
            }
        },
		moveCarouselDot(index) {
			this.divActive = index
            this.disable = true
            let active = this.divActive
            console.log(active)

            if(active > index) {
                console.log(true)
            } else {
                console.log(false)
            }

			setTimeout(() => {
				this.disable = false
			}, 1000)
		}
    },
}
</script>