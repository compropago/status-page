<template>
  <div id="app">
    <div class="header">
      <status-header :icon="'✅'"
                     :title="'All systems operational'"
                     :status="'Refreshed 30 min ago'"
                     :className="'success'"></status-header>
      <status-header :icon="'⚠️'"
                     :title="'All systems operational'"
                     :status="'Refreshed 30 min ago'"
                     :className="'warning'"></status-header>
      <status-header :icon="'⚠️'"
                     :title="'Webhooks degraded performance'"
                     :status="'Refreshed 30 min ago'"
                     :className="'danger'"></status-header>
    </div>
    <div class="about">
      <p class="about-title title">About this Site</p>
      <p class="about-description">Welcome to ComproPagos's home for real-time information and updates on our applications.</p>
      <p class="about-description">Here you'll find live and historical data on system performance and metrics. If there are any service interruptions, a note will be posted here.</p>
    </div>
    <div class="status-timelines">
      <div class="status">
        <span class="status-title title">Microserves</span>
        <div class="status-bars">
          <status-bar v-for="day in days"
          :className="day.status"
          :date="day.detail.date"
          :message="day.detail.message"></status-bar>
        </div>
        <div class="status-timeline">
          <time-line :startDay="'90 days ago'"
                     :upTime="'99% Uptime'"
                     :endDay="'Today'"></time-line>
        </div>
      </div>
      <div class="status">
        <span class="status-title title">Website / Panel</span>
        <div class="status-bars">
          <status-bar v-for="day in days"
          :className="day.status"
          :date="day.detail.date"
          :message="day.detail.message"></status-bar>
        </div>
        <div class="status-timeline">
          <time-line :startDay="'90 days ago'"
                     :upTime="'99% Uptime'"
                     :endDay="'Today'"></time-line>
        </div>
      </div>
    </div>
    <div class="incidents">
      <div class="incidents-header">
        <p class="incidents-title title">Past Incidents</p>
        <a href="#">View Archive</a>
      </div>
      <logs v-for="log in logs"
            :detail="log.detail"
            :title="log.title"
            :status="log.status"
            :info="log.info"></logs>
    </div>
  </div>
</template>

<script>
import StatusBar from './components/StatusBar';
import TimeLine from './components/TimeLine';
import StatusHeader from './components/StatusHeader';
import Logs from './components/Logs';

export default {
  name: 'app',
  components: {
    StatusBar,
    TimeLine,
    StatusHeader,
    Logs,
  },
  data() {
    return {
      logs: [
        {
          detail: 'Aug 15, 2017 19:57 UTC',
          title: 'Issues with API Lorem Ipsum',
          status: 'Resolved',
          info: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque ultrices quis ligula in aliquam. Sed eget sodales sem. Pellentesque a gravida dui, at justo. Proin euismod risus mi. Aliquam erat volutpat. Ut id dignissim massa. Proin sollicitudin lacinia quam, ac feugiat ante lobortis eu.',
        },
        {
          detail: 'Aug 15, 2017 19:57 UTC',
          title: 'Issues with API Lorem Ipsum',
          status: 'Resolved',
          info: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque ultrices quis ligula in aliquam. Sed eget sodales sem. Pellentesque a gravida dui, at justo. Proin euismod risus mi. Aliquam erat volutpat. Ut id dignissim massa. Proin sollicitudin lacinia quam, ac feugiat ante lobortis eu.',
        },
        {
          detail: 'Aug 15, 2017 19:57 UTC',
          title: 'Issues with API Lorem Ipsum',
          status: 'Resolved',
          info: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque ultrices quis ligula in aliquam. Sed eget sodales sem. Pellentesque a gravida dui, at justo. Proin euismod risus mi. Aliquam erat volutpat. Ut id dignissim massa. Proin sollicitudin lacinia quam, ac feugiat ante lobortis eu.',
        },
        {
          detail: 'Aug 15, 2017 19:57 UTC',
          title: 'Issues with API Lorem Ipsum',
          status: 'Resolved',
          info: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque ultrices quis ligula in aliquam. Sed eget sodales sem. Pellentesque a gravida dui, at justo. Proin euismod risus mi. Aliquam erat volutpat. Ut id dignissim massa. Proin sollicitudin lacinia quam, ac feugiat ante lobortis eu.',
        },
        {
          detail: 'Aug 15, 2017 19:57 UTC',
          title: 'Issues with API Lorem Ipsum',
          status: 'Resolved',
          info: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque ultrices quis ligula in aliquam. Sed eget sodales sem. Pellentesque a gravida dui, at justo. Proin euismod risus mi. Aliquam erat volutpat. Ut id dignissim massa. Proin sollicitudin lacinia quam, ac feugiat ante lobortis eu.',
        },
        {
          detail: 'Aug 15, 2017 19:57 UTC',
          title: 'Issues with API Lorem Ipsum',
          status: 'Resolved',
          info: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque ultrices quis ligula in aliquam. Sed eget sodales sem. Pellentesque a gravida dui, at justo. Proin euismod risus mi. Aliquam erat volutpat. Ut id dignissim massa. Proin sollicitudin lacinia quam, ac feugiat ante lobortis eu.',
        },
        {
          detail: 'Aug 15, 2017 19:57 UTC',
          title: 'Issues with API Lorem Ipsum',
          status: 'Resolved',
          info: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque ultrices quis ligula in aliquam. Sed eget sodales sem. Pellentesque a gravida dui, at justo. Proin euismod risus mi. Aliquam erat volutpat. Ut id dignissim massa. Proin sollicitudin lacinia quam, ac feugiat ante lobortis eu.',
        },
        {
          detail: 'Aug 15, 2017 19:57 UTC',
          title: 'Issues with API Lorem Ipsum',
          status: 'Resolved',
          info: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque ultrices quis ligula in aliquam. Sed eget sodales sem. Pellentesque a gravida dui, at justo. Proin euismod risus mi. Aliquam erat volutpat. Ut id dignissim massa. Proin sollicitudin lacinia quam, ac feugiat ante lobortis eu.',
        },
      ],
      days: [
        { status: 'danger',
          detail: {
            message: 'Well, the way they make shows is, they make one show. That shows called a pilot.',
            date: '10/9/17',
          } },
        { status: 'warning',
          detail: {
            message: "Then they show that show to the people who make shows, and on the strength of that one show they decide if they're going to make more shows.",
            date: '15/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
        { status: 'success',
          detail: {
            message: " Some don't, become nothing. She starred in one of the ones that became nothing",
            date: '19/9/17',
          },
        },
      ],
    };
  },
};
</script>

<style>
.title {
  color: #16325C;
  font-size: 1.2rem;
}
.about {
  margin: 2rem 0;
  text-align: left;
}
.about-title {
  margin-bottom: 1rem;
}
.status {
  margin-bottom: 2rem;
}
.status-title {
  text-align: left;
}
.status-timelines {
  border: 1px solid #B1C3CF;
  padding: 1rem 2rem;
}
.incidents {
  margin-top: 1rem;
}
.incidents-header {
  display: flex;
  justify-content: space-between;
  padding: 1rem 0;
}
.status-bars {
  display: flex;
  justify-content: space-between;
  margin-top: 1rem;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
p {
  margin: 0;
}
</style>
