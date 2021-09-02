<template>
    <div class="holder" :class="{'close' : sideBarClose}">
            <div class="top">
                <div class="menu"> 
                    <span class="title">Sachemo</span>
                    <div class="menu-wrapper">
                        <div class="hamburger" v-on:click="closeSideBar()">
                            <div class="line"></div>
                            <div class="line-middle"></div>
                            <div class="line-end"></div> 
                        </div>
                        <span class="title-mobile">Sa.</span>                    
                    </div>
                </div>
                <div class="middle">
                    <p class='sub-title'>NAVIGATION</p>
                    <div class="first">
                        <div  class="loop" v-for="(navigation, index) in navigations" :key="navigation.id"
                        :style="index === navigations.length - 1 ? {'margin-bottom' : '0px'} : {'margin-bottom' : '18px'}"
                        >
                            <div class="desc">
                                <img class="logo" :src="`/${navigation.logo}`"/>
                                <p >{{navigation.name}}</p>
                            </div>
                            <div class="count" :style="[navigation.countNotification ? {'background': navigation.notifColor} : {'background': '#FFF'}]">
                                <p v-if="navigation.countNotification != null">{{navigation.countNotification}}</p>
                            </div>
                        </div>
                    </div>
                    <div class="second">
                        <p class='sub-title'>INSIGHT</p>
                        <div class="loop" v-for="(insight, index) in insights" v-bind:key="insight.id"
                        :style="index === insights.length - 1 ? {'margin-bottom' : '0px'} : {'margin-bottom' : '18px'}">
                            <div class="desc">
                                <img class="logo" :src="`/${insight.logo}`"/>
                                <p>{{insight.name}}</p>
                            </div>
                            <div class="count" :style="[insight.countNotification ? {'background': insight.notifColor} : {'background': '#FFF'}]">
                                <p v-if="insight.countNotification != null" >{{insight.countNotification}}</p>
                            </div>
                        </div>
                    </div>           
                </div>
            </div>
            <div class="bottom">
                <div class="bottom-wrapper">
                    <img class="avatar" :src="`/${profil.avatar}`"/>
                    <div class="bottom-wrapper-desc">
                        <p class="bottom-wrapper-desc-name">{{profil.name}}</p>
                        <p class="bottom-wrapper-desc-email">{{profil.email}}</p>
                    </div>
                </div>
                <img class="logo-arrow" src="/arrow.png" />
            </div>        
        </div>
</template>

<script>
export default {
    data(){
        return {
            navigations :[
                { id: 1, logo: 'dashboard.png', name: 'DashBoard', countNotification: null, notifColor : null},
                { id: 2, logo: 'orders.png', name: 'Orders', countNotification: 243, notifColor : '#ffd475'},
                { id: 3, logo: 'products.png', name: 'Products', countNotification: 83, notifColor : '#2dbbb1'},
                { id: 4, logo: 'payments.png', name: 'Payments', countNotification: null, notifColor : null},
                { id: 5, logo: 'users.png', name: 'Users', countNotification: '32k', notifColor : '#FBAF7D'},
                { id: 6, logo: 'campaings.png', name: 'Campaings', countNotification: null, notifColor : null}
            ],

            insights :[
                { id: 1, logo: 'inbox.png', name: 'Inbox', countNotification: 84, notifColor : '#3e67c6'},
                { id: 2, logo: 'notifications.png', name: 'Notifications', countNotification: 12, notifColor : '#f15569'},
                { id: 3, logo: 'chat.png', name: 'Chat', countNotification: 43, notifColor : '#61509e'},
            ],

            profil : { id: 1, avatar: 'long-dehez.jpg', name: 'Michael Gabson', email: 'michael@gmail.com'},

            sideBarClose : false,
        }
    },

    methods : {
        closeSideBar :  function(){
            this.sideBarClose = !this.sideBarClose
            console.log(this.sideBarClose)
        }
    }
}

</script>

<style lang="scss">

.holder{
    
    height: 650px;
    width: 270px;
    padding: 20px;
    background: #ffffff;
    border-radius: 24px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    box-shadow: 4px 4px 24px rgba(0, 0, 0, 0.08);
    transition: width 1s;

    .top{
        margin-bottom: 24px;
    }

    .menu{
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: flex-start;
        margin-bottom: 18px;
    }

    .title{
        font-weight: bold;
        font-size: 14px;
        color: #242424;
        transition: opacity 1, width 1, height 1s;
    }

    .title-mobile{
        font-weight: bold;
        font-size: 14px;
        color: #242424;
        opacity: 0;
        transition: opacity .5s;
    }

    .hamburger{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: 16px;
        cursor: pointer;
        margin-bottom: 18px;
    }

    .line, .line-end{
        width: 100%;
        padding: 0;
        height: 1px;
        background: #494949;
        transition: width .5s;
        animation-delay: 1s;
    }

    .line-middle{
        padding: 0;
        width: 100%;
        height: 1px;
        background: #494949;
        margin-top: 4px;
        margin-bottom: 4px;
        transition: width .5s;
        animation-delay: 1s;
    }

    .middle{
        display: flex;
        flex-direction: column;
        justify-content: center;
    }

    .first{
        margin-bottom: 32px;
    }

    .loop{
        display: flex;
        flex-direction: row;
        align-items: flex-start;
        justify-content: space-between;
        cursor: pointer;

        &:hover .desc{
            font-weight: bold;
            color: black;
        }
    }

    .desc{
        display: grid;
        grid-template-columns: repeat(2, 0fr);
        grid-gap: 12px;
        color: #9399a9;
        align-items: center;
    }

    .desc > p{
        transition: opacity .5s, width 1s, height 1s,;
    }

    .count{
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: 18px;
        padding: 4px;
        color: white;
        font-size: 12px;
    }

    .bottom{
        border: 1px solid #eaeaec;;
        border-radius: 20px;
        padding-top: 8px;
        padding-left: 8px;
        padding-bottom: 8px;
        padding-right: 16px;
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .bottom-wrapper{
        display: grid;
        grid-template-columns: repeat(2, 0fr);
        grid-gap: 8px;
    }

    .avatar{
        width: 30px;
        border-radius: 50%;
    }

    .bottom-wrapper-desc{
        display: flex;
        flex-direction: column;
        justify-content: center;
        transition: opacity .5s, width 1.5s, height 1.5s,;
    }

    .bottom-wrapper-desc-name{
        font-weight: bold;
        color: #242424;
        font-size: 9px;
    }
    .bottom-wrapper-desc-email{
        color: #9399a9;
        font-size: 8px;
    }

    .logo{
        width: 18px;
    }

    .logo-arrow{
        width: 12px;
        cursor: pointer;
    }

    .sub-title{
        font-size: 10px;
        font-weight: bold;
        margin-bottom: 24px;
        color: #242424;
        transition: opacity .5s;
    }

    &.close{
        padding: 20px 10px;
        width: 70px;

        .line-middle{
            width: 80%;
        }

        .line-end{
            width: 60%;
        }

        .menu-wrapper{
            padding-left: 13px;
        }

        .menu-wrapper{
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding-right: 30px;
        }

        .sub-title{
            opacity: 0;
        }

        .title{
            opacity: 0;
            height: 0;
            width: 0;
            overflow: hidden;
        }
        
        .count > p,.logo-arrow{
            display: none;
        }


        .desc > p{
            opacity: 0;
            width: 0;
            height: 0;
            overflow: hidden;
        }

        .title-mobile{
            opacity: 100%;
        }

        .desc{
            display: flex;
            justify-content: flex-start;
            align-items: flex-start;
            width: 18px;
        }

        .loop{
            padding-left: 13px;
            display: flex;
            justify-content: flex-start;
            align-items: flex-start;
        }

        .count{
            padding: 3px;
            margin-left: 2px;
        }

        .bottom{
            padding: 8px;
        }

        .avatar{
            margin: 0;
        }

        .bottom-wrapper-desc{
            opacity: 0;
            width: 0;
            height: 0;
            overflow: hidden;
        }
    }
}
</style>
