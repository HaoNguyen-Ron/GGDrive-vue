<script setup lang="ts">
const post = {
  title: 'Công ty S-tour Cần tuyển HDV',
  description: ' Chúng tôi đang cần HDV cho tour Đà Nẵng - Hội An - Huế cho đoàn gồm 5 khách Úc và 3 khách Đài Loan',
  tourist_number: 8,
  price: 300,
  departure_time: '9:00am 12/12/2077',
  departure_location: 'Big C Đà Nẵng',
  created_at: '01/01/2077',
  current_apply: 10,
  current_deal: 2,
  total_destinations: [
    {
      id: 0,
      name: 'Đà Nẵng',
    },
    {
      id: 1,
      name: 'Hội An',
    },
    {
      id: 2,
      name: 'Huế',
    },
  ],

  required_skill: [
    {
      id: 0,
      key: 'language',
      value: 'Tiếng Anh',
    },
    {
      id: 1,
      key: 'language',
      value: 'Tiếng Trung',
    },
    {
      id: 2,
      key: 'experience',
      value: 12, // MONTH
    },
  ],
  partner_attributes: [
    {
      id: 0,
      key: 'phone number',
      status: 'đã kiểm định',
    },
    {
      id: 1,
      key: 'address',
      status: 'đã kiểm định',
    },
    {
      id: 2,
      key: 'payment type',
      status: 'chưa kiểm định',
    },
  ],

}
function handlePayLoad(price: number) {
  return `${price}.000 VND`
}

function getLabel(attribute: {
  id: number
  key: string
  value: string | number
}) {
  switch (attribute.key) {
    case 'experience':

      return `${attribute.value as number / 12} năm kinh nghiệm`

    default:
      return attribute.value
  }
}
</script>

<template>
  <div :class="$style.postDetailWrapper">
    <div :class="$style.postDetailHeader">
      <h2 :class="$style.postDetailHeaderTitle">
        {{ post.title }}
      </h2>

      <p :class="$style.postDetailNote" class="mb-1">
        Đã đăng lúc {{ post.created_at }}
      </p>

      <div :class="$style.postDetailHeaderList">
        <span
          v-for="destination in post.total_destinations" :key="`destination-${destination.id}`"
          :class="$style.postDetailItem"
        >
          <i class="fa-solid fa-location-dot postDetailIcon" />

          <div :class="$style.postDetailContent">
            {{ destination.name }}
          </div>
        </span>
      </div>
    </div>

    <section :class="[$style.postDetailContent, $style.postDetailSection]">
      {{ post.description }}
    </section>

    <div :class="[$style.postDetailDescriptionList, $style.postDetailSection]">
      <div :class="$style.postDetailItem">
        <i class="fa-solid fa-money-bill" :class="$style.postDetailIcon" />

        <div :class="$style.postDetailContent">
          <strong :class="$style.postDetailTitle">
            {{ handlePayLoad(post.price) }} / ngày
          </strong>

          <div :class="$style.postDetailNote">
            Tiền công trên một ngày
          </div>
        </div>
      </div>

      <div :class="$style.postDetailItem">
        <i class="fa-solid fa-people-group" :class="$style.postDetailIcon" />

        <div :class="$style.postDetailContent">
          <strong :class="$style.postDetailTitle">
            {{ post.tourist_number }} / người
          </strong>

          <div :class="$style.postDetailNote">
            Số lượng khách du lịch
          </div>
        </div>
      </div>

      <div :class="$style.postDetailItem">
        <i class="fa-solid fa-street-view" :class="$style.postDetailIcon" />

        <div :class="$style.postDetailContent">
          <strong :class="$style.postDetailTitle">
            {{ post.departure_location }}
          </strong>

          <div :class="$style.postDetailNote">
            Vị trí khởi hành
          </div>
        </div>
      </div>

      <div :class="$style.postDetailItem">
        <i class="fa-solid fa-clock" :class="$style.postDetailIcon" />

        <div :class="$style.postDetailContent">
          <strong :class="$style.postDetailTitle">
            {{ post.departure_time }}
          </strong>

          <div :class="$style.postDetailNote">
            Thời gian khởi hành
          </div>
        </div>
      </div>
    </div>

    <div :class="$style.postDetailSection">
      <h2 :class="$style.postDetailHeading">
        Yêu cầu về trình độ
      </h2>

      <div :class="$style.postDetailBagdeList">
        <span v-for="skill in post.required_skill" :key="skill.id" :class="$style.postDetailBagde">
          {{ getLabel(skill) }}
        </span>
      </div>
    </div>

    <div :class="$style.postDetailSection">
      <h2 :class="$style.postDetailHeading">
        Thông tin về tuyển dụng
      </h2>

      <div :class="$style.postDetailList">
        <div :class="$style.postDetailActivity">
          <div :class="$style.postDetailTitle">
            Tổng số ứng tuyển hiện tại:
          </div>
  
          <div :class="$style.postDetailContent">
            {{ post.current_apply}}
          </div>
        </div>

        <div :class="$style.postDetailActivity">
          <div :class="$style.postDetailTitle">
            Tổng số ứng tuyển đang thỏa thuận:
          </div>
  
          <div :class="$style.postDetailContent">
            {{ post.current_deal}}
          </div>
        </div>
      </div>
    </div>

    <div :class="$style.postDetailSection">
      <h2 :class="$style.postDetailHeading">
        Thông tin về nhà tuyển dụng
      </h2>

      <div :class="$style.postDetailList">
        <div v-for="attribute in post.partner_attributes" :key="attribute.id" :class="$style.postDetailItem">
          <i v-if="attribute.status === 'đã kiểm định'" class="fa-solid fa-square-check " :class="[$style.postDetailIconGreen, $style.postDetailIcon]" />

          <i v-else class="fa-solid fa-circle-xmark" :class="[$style.postDetailIconRed, $style.postDetailIcon]" />

          <p :class="$style.postDetailNote" >{{ attribute.key }} {{ attribute.status }}</p>
        </div>
      </div>
    </div>

    <div :class="$style.postDetailFooter">
      <button :class="[$style.postDetailBtn, $style.postDetailBtnPrimary]">
        Nộp đơn
      </button>

      <button :class="[$style.postDetailBtn, $style.postDetailBtnOutline]">
        Lưu bài viết
      </button>
    </div>
  </div>
</template>

<style lang="scss" module>
.postDetailWrapper {
  background-color: white;
}

.postDetailHeader {
  padding: 24px 16px;
  border-bottom: 1px solid var(--color-gray-lighter);
}

.postDetailSection {
  padding: 24px 16px;
  border-bottom: 1px solid var(--color-gray-lighter);
}

.postDetailHeaderTitle {
  font-size: 16px;
  font-weight: 500;
  letter-spacing: .32px;
  line-height: 22px;
}

.postDetailHeaderList {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.postDetailFooter {
  background-color: white;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 10px;
  padding: 16px;
}

.postDetailDescriptionList {
  display: flex;
  flex-direction: column;
  gap: 32px;
}

.postDetailList {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.postDetailItem {
  display: flex;
  align-items: center;
  gap: 10px;
}

.postDetailBagdeList {
  display: flex;
  gap: 10px;
  flex-wrap: wrap
}

.postDetailBagde {
  display: inline-flex;
  background-color: var(--color-gray-lighter);
  color: var(--color-gray-darker);
  gap: normal 8px;
  padding: 0 12px;
  border-radius: 20px;
  line-height: 33px;
}

.postDetailActivity {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.postDetailVerification {
  padding: 2rem 0;
}

.postDetailHeading {
  font-weight: 500;
  font-size: 20px;
  letter-spacing:.4px;
  line-height: 24px;
  margin: 0;
  margin-bottom: 10px;
}

.postDetailContent {
  font-size: 14px;
  letter-spacing: .32px;
  line-height: 22px;
}

.postDetailTitle {
  font-size: 14px;
  line-height: 22px;
  text-align: left;
  font-weight: 500;
}

.postDetailNote {
  color: var(--color-gray);
  font-size: 12px;
  line-height: 20px;
}

.postDetailIcon {
  font-size: 22px;
  display:inline-block;
}

.postDetailIconGreen {
  color: green;
  font-size: 22px;
}

.postDetailIconRed {
  color: red;
}

.postDetailBtn {
    font-size: 16px;
    padding: 0 24px;
    border-radius: 160px;
    line-height: 39px;
    letter-spacing: .3px;
    text-align: center;
    outline: none;
    cursor: pointer;
    transition-duration: 300ms;

    &:hover {
      color: white;
      background-color: var(--color-primary-dark);
    }

    &:active {
      color: white;
      background-color: var(--color-primary-darker);
    }

  }
  .postDetailBtnPrimary {
    border: none;
    background-color: var(--color-primary);
    color: white;
  }

  .postDetailBtnOutline {
    border: 2px solid var(--color-primary);
    color: var(--color-primary);
    background-color: white;
  }
</style>
