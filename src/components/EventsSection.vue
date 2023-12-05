<script>
export default {
    data() {
        return{
            events: [
                {
                    date: "Jan 7, 2022",
                    start: "9:00 am",
                    end: "5:00 pm",
                    title: "Melbourne Coaching",
                    location: "Cambridge, MA 02138, USA",
                    info: {
                        text: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Eius illum accusamus incidunt voluptas ut est qui.",
                        active: true
                    }
                },
                {
                    date: "Jan 11, 2022",
                    start: "9:00 am",
                    end: "5:00 pm",
                    title: "New York Coaching",
                    location: "Cambridge, MA 02138, USA",
                    info: {
                        text: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Eius illum accusamus incidunt voluptas ut est qui.",
                        active: false
                    }
                },
                {
                    date: "Jan 21, 2022",
                    start: "9:00 am",
                    end: "5:00 pm",
                    title: "London Coaching",
                    location: "Cambridge, MA 02138, USA",
                    info: {
                        text: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Eius illum accusamus incidunt voluptas ut est qui.",
                        active: false
                    }
                }
            ],
            btn: "READ MORE",
        }
    },
    methods: {
        getDayFormat(date) {
            let day;

            if(date.length==11){
                day= "0"+date.charAt(4);
                return day; 
            } else {
                day= date.substring(4,6);
                return day;
            }
        },
        getMonth(date){
            let month;

            month = date.substring(0,3)+', '+date.substring(date.length-5, date.length);
            return month;
        },
        openInfo(obj){  
            if(obj.info.active){
                obj.info.active=false;
                this.btn="READ MORE";
            }else{
                obj.info.active=true;
                this.btn="CLOSE";
            }
        }
    }
}
</script>

<template>
    <div class="container">
        <div class="events-box">
            <div class="events-title">
                <h2 class="title">Upcoming Events</h2>
            </div>

            <div class="event" v-for="(event, i) in events">
                <div class="date">
                    <span class="day">{{ getDayFormat(event.date) }}</span>
                    <small>{{ getMonth(event.date) }}</small>
                </div>
                <div class="event-description">
                    <h4 class="title">{{ event.title }}</h4>
                    <div class="time">
                        <small>
                            <i class="fa-regular fa-clock"></i>
                            {{ event.start }} - {{ event.end }}, {{ event.date }}
                        </small>
                    </div>
                    <div class="place">
                        <small>
                            <i class="fa-solid fa-location-dot"></i>
                            {{ event.location }}
                        </small>
                    </div>
                    <button  @click="openInfo(event)">{{ btn }}</button>

                    <div class="info" :class="event.info.active? 'open': 'closed'">{{ event.info.text }}</div>
                </div>
            </div>
        </div>

    </div>
</template>

<style scoped lang="scss">
@use '../style/general.scss' as *;
@use '../style/partials/variables' as *;

.container {
    width: 100%;
    height: 100vh;
    background-image: url("../assets/img/img/h1-img-09.jpg");
    background-size: cover;

    .events-box {
        width: 25%;
        position: relative;
        top: 50%;
        left: 25%;
        transform: translate(-25%, -50%);
        .events-title {
            background-color: white;
            padding: .8rem;
            box-shadow: 0 5px 10px $border_events;
            position: relative;
        }

        .event {
            background-color: white;
            border-bottom: 1px solid $border_events;
            display: flex;
            justify-content: center;
            padding: 1.5rem;
            .date {
                width: 3.5rem;
                height: 2.5rem;
                background-color: $main_color;
                color: white;
                font-family: serif;
                text-align: center;
                padding: .3rem;

                .day {
                    font-weight: bold;
                    font-size: .8rem;
                }
            }

            .event-description {
                margin-left: 1rem;

                & small {
                    line-height: 1.5rem;
                    color: $gray_text;
                    i {
                        color: $main_color;
                    }
                }

                button{
                    border: 0;
                    background-color: white;
                    font-weight: bold;
                    font-size: .6rem;
                }

                .info{
                    font-size: .8rem;
                }
            }

        }
    }

}

small {
    display: block;
    font-size: .6rem;
}

.open{
    display:block;
}

.closed{
    display: none;
}


</style>