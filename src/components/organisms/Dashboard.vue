<template>
  <article class="dashboard">
    <section class="dashboard__follower-status">
      <div class="card-container">
        <template v-for="media in medias">
          <Card
            :key="media.type"
            :media="media"
          />
        </template>
      </div>
    </section>
    <section class="dashboard__overview-today">
      <h2 class="title">Overview - Today</h2>
      <div class="card-container">
        <template v-for="status in statuses">
          <ActiveStatusCard
            :key="status.id"
            :status="status"
          />
        </template>
      </div>
    </section>
  </article>
</template>

<script>
import Card from '@/components/molecules/Card';
import ActiveStatusCard from '@/components/molecules/ActiveStatusCard';
export default {
  components: {
    Card,
    ActiveStatusCard
  },
  data() {
    return {
      medias: [
        {
          type: "facebook",
          account: "@nathanf",
          follower: "1987",
          increase: "12",
        },
        {
          type: "twitter",
          account: "@nathanf",
          follower: "1044",
          increase: "99",
        },
        {
          type: "instagram",
          account: "@realnathanf",
          follower: "11k",
          increase: "1099",
        },
        {
          type: "youtube",
          account: "Nathan F.",
          follower: "239",
          decrease: "144",
        },
      ],
      statuses: [
        {
          id: 1,
          type: 'Page Views',
          media: 'facebook',
          currentNumber: 87,
          percentage: {
            type: 'up',
            number: 3
          },
        },
        {
          id: 2,
          type: 'Likes',
          media: 'facebook',
          currentNumber: 52,
          percentage: {
            type: 'down',
            number: 2
          },
        },
        {
          id: 3,
          type: 'Likes',
          media: 'instagram',
          currentNumber: 5462,
          percentage: {
            type: 'up',
            number: 2257
          },
        },
        {
          id: 4,
          type: 'Profile Views',
          media: 'instagram',
          currentNumber: '52k',
          percentage: {
            type: 'up',
            number: 1375
          },
        },
        {
          id: 5,
          type: 'Retweets',
          media: 'twitter',
          currentNumber: 117,
          percentage: {
            type: 'up',
            number: 303
          },
        },
        {
          id: 6,
          type: 'Likes',
          media: 'twitter',
          currentNumber: 507,
          percentage: {
            type: 'up',
            number: 553
          },
        },
        {
          id: 7,
          type: 'Likes',
          media: 'youtube',
          currentNumber: 107,
          percentage: {
            type: 'down',
            number: 19
          },
        },
        {
          id: 8,
          type: 'Total Views',
          media: 'youtube',
          currentNumber: 1407,
          percentage: {
            type: 'down',
            number: 12
          },
        },
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
@import "@/styles/scss/_variable.scss";
.dashboard {
  height: 100%;
  &__follower-status {
    margin-bottom: 40px;
  }
  &__overview-today {
    .title {
      font-size: $fs-700;
      font-weight: 700;
      margin-bottom: 20px;
    }
  }
}
.card-container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 20px;
}
@media only screen and (max-width: 850px) {
  .card-container {
    grid-template-columns: 1fr;
  }
}
</style>