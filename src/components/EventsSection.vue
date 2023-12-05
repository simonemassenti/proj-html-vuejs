<script>
export default {
    data() {
        return {
            events: [
                {
                    date: "Jan 7, 2022",
                    start: "9:00 am",
                    end: "5:00 pm",
                    title: "Melbourne Coaching",
                    location: "Cambridge, MA 02138, USA",
                    info: {
                        text: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Eius illum accusamus incidunt voluptas ut est qui.",
                        active: false
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
            ]
        }
    },
    methods: {
        getDayFormat(date) {
            let day;

            if (date.length == 11) {
                day = "0" + date.charAt(4);
                return day;
            } else {
                day = date.substring(4, 6);
                return day;
            }
        },
        getMonth(date) {
            let month;

            month = date.substring(0, 3) + ', ' + date.substring(date.length - 5, date.length);
            return month;
        },
        openInfo(obj) {
            if (obj.info.active) {
                obj.info.active = false;
            } else {
                obj.info.active = true;
            }
        }
    }
}
</script>

<template>
    <div class="container">
        <div class="events-box">
            <div class="events-title">
                <h3 class="title">Upcoming Events</h3>
            </div>

            <div class="event" v-for="event in events">
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
                    <button @click="openInfo(event)" class="btn-rm">
                        <span v-if="event.info.active">CLOSE</span>
                        <span v-else>READ MORE</span>
                    </button>

                    <div class="info" v-if="event.info.active">{{ event.info.text }}</div>
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
        width: 28%;
        position: relative;
        top: 50%;
        left: 20%;
        transform: translate(-25%, -50%);

        .events-title {
            background-color: white;
            padding: 1rem 2rem;
            box-shadow: 0 5px 10px $border_gray;
            position: relative;
        }

        .event {
            background-color: white;
            border-bottom: 1px solid $border_events;
            display: flex;
            padding: 1.5rem 2rem;

            .date {
                width: 3rem;
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

                small {
                    display: block;
                    font-size: .5rem;
                }
            }

            .event-description {
                max-width: 70%;
                margin-left: 1.5rem;
                & small {
                    line-height: 1.5rem;
                    color: $gray_text;
                    font-size: .6rem;
                    i {
                        color: $main_color;
                        margin-right: .5rem;
                    }
                }

                .info {
                    font-size: .8rem;

                }
            }

        }
    }

}
</style>