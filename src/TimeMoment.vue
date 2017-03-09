<template>
    <div :class="classes" :title="timeStart">{{ timeNow }}</div>
</template>

<script type="text/babel">
    import moment from 'moment';

    export default {
        name: 'time-moment',
        props: {
            classes: {
                type: [String, Array],
                default: 'time',
            },
            timeStart: {
                required: true,
                validator(value) {
                    return moment(value)._isValid;
                },
            },
        },
        data() {
            return {
                timeNow: moment(this.timeStart).fromNow(),
            };
        },
        created() {
            setInterval(() => {
                this.timeNow = moment(this.timeStart).fromNow();
            }, 1000);
        },
    };
</script>
