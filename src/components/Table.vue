<template>
  <div ref="table" class="table">
    <div ref="fixed" class="fixed">
      <div class="head-sticky row">
        <div></div>
        <div>Клиент</div>
      </div>
      <div class="row">
        <div></div>
        <div>Камчаткин Андрей Николаевич</div>
      </div>
      <div class="row">
        <div></div>
        <div>Камчаткин Андрей Николаевич 2</div>
      </div>
      <div class="row">
        <div></div>
        <div>Камчаткин Андрей Николаевич 3</div>
      </div>
      <div class="row">
        <div></div>
        <div>Камчаткин Андрей Николаевич 4</div>
      </div>
      <div class="row">
        <div></div>
        <div>Камчаткин Андрей Николаевич 5</div>
      </div>
      <div class="row">
        <div></div>
        <div>Камчаткин Андрей Николаевич 6</div>
      </div>
      <div class="row">
        <div></div>
        <div>Камчаткин Андрей Николаевич 7</div>
      </div>
      <div class="row">
        <div></div>
        <div>Камчаткин Андрей Николаевич 8</div>
      </div>
      <div class="row">
        <div></div>
        <div>Камчаткин Андрей Николаевич 9</div>
      </div>
      <div class="row">
        <div></div>
        <div>Камчаткин Андрей Николаевич 10</div>
      </div>
    </div>
    <div ref="auto" class="auto">
      <div class="head-sticky row">
        <div>Всего проектов</div>
        <div>Всего кампаний</div>
        <div>Email</div>
        <div>Время добавления</div>
        <div>Статус</div>
        <div></div>
      </div>
      <div class="row">
        <div>1</div>
        <div>0</div>
        <div>oksana.kam4atkina@ukr.net</div>
        <div><span>04.08.2023</span>18:54</div>
        <div>Активный</div>
        <div><button>просмотреть</button></div>
      </div>
      <div class="row">
        <div>1</div>
        <div>0</div>
        <div>oksana.kam4atkina@ukr.net</div>
        <div><span>04.08.2023</span>18:54</div>
        <div>Активный</div>
        <div><button>просмотреть</button></div>
      </div>
      <div class="row">
        <div>1</div>
        <div>0</div>
        <div>oksana.kam4atkina@ukr.net</div>
        <div><span>04.08.2023</span>18:54</div>
        <div>Активный</div>
        <div><button>просмотреть</button></div>
      </div>
      <div class="row">
        <div>1</div>
        <div>0</div>
        <div>oksana.kam4atkina@ukr.net</div>
        <div><span>04.08.2023</span>18:54</div>
        <div>Активный</div>
        <div><button>просмотреть</button></div>
      </div>
      <div class="row">
        <div>1</div>
        <div>0</div>
        <div>oksana.kam4atkina@ukr.net</div>
        <div><span>04.08.2023</span>18:54</div>
        <div>Активный</div>
        <div><button>просмотреть</button></div>
      </div>
      <div class="row">
        <div>1</div>
        <div>0</div>
        <div>oksana.kam4atkina@ukr.net</div>
        <div><span>04.08.2023</span>18:54</div>
        <div>Активный</div>
        <div><button>просмотреть</button></div>
      </div>
      <div class="row">
        <div>1</div>
        <div>0</div>
        <div>oksana.kam4atkina@ukr.net</div>
        <div><span>04.08.2023</span>18:54</div>
        <div>Активный</div>
        <div><button>просмотреть</button></div>
      </div>
      <div class="row">
        <div>1</div>
        <div>0</div>
        <div>oksana.kam4atkina@ukr.net</div>
        <div><span>04.08.2023</span>18:54</div>
        <div>Активный</div>
        <div><button>просмотреть</button></div>
      </div>
      <div class="row">
        <div>1</div>
        <div>0</div>
        <div>
          oksana.kam4atkina@ukr2.net oksana.kam4atkina@ukr1.net
          oksana.kam4atkina@ukr3.net oksana.kam4atkina@ukr.net
        </div>
        <div><span>04.08.2023</span>18:54</div>
        <div>Активный</div>
        <div><button>просмотреть</button></div>
      </div>
      <div class="row">
        <div>1</div>
        <div>0</div>
        <div>oksana.kam4atkina@ukr.net</div>
        <div><span>04.08.2023</span>18:54</div>
        <div>Активный</div>
        <div><button>просмотреть</button></div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data: () => ({
    stickys: [],
    table: null,
    scrollBox: null,
    scrollTrigger: null,
    triggerOnScrolLTrigger: false,
    //
    currentScreenWidth: 0,
  }),
  methods: {
    scopeResize() {
      if (this.currentScreenWidth == document.documentElement.offsetWidth)
        return null;
      this.currentScreenWidth == document.documentElement.offsetWidth;
      this.stickyChecker();
      this.createStickyScroll();
      this.rowHeightChecker();
      if (this.scrollTrigger) this.stickyScrollChecker();
    },
    scopeScroll() {
      this.stickyChecker();
      if (this.scrollTrigger) this.stickyScrollChecker();
    },
    stickyChecker() {
      try {
        if (!this.stickys.length)
          this.stickys = [
            this.$refs.fixed.querySelector('.row.head-sticky'),
            this.$refs.auto.querySelector('.row.head-sticky'),
          ];
        if (!this.table)
          this.table = this.$refs.table || document.querySelector('.table');
        const optionalHeaderHeight =
          document.querySelector('header')?.scrollHeight || 0;
        const top = this.table.getBoundingClientRect().top;
        const tableH = this.table.scrollHeight;
        const topPos = top + window.pageYOffset;
        if (window.pageYOffset + optionalHeaderHeight > topPos) {
          const optionalScrollHeight = this.scrollBox
            ? this.scrollBox.offsetHeight
            : 0;
          let val = window.pageYOffset + optionalHeaderHeight - topPos;
          this.stickys.forEach((item) => {
            item.classList.add('move');
            if (item.scrollHeight + val < tableH - optionalScrollHeight) {
              item.style.top = val + 'px';
            } else {
              item.style.top =
                tableH - optionalScrollHeight - item.scrollHeight + 'px';
            }
          });
        } else {
          this.stickys.forEach((item) => {
            item.classList.remove('move');
            item.style.top = 0;
          });
        }
      } catch (e) {
        console.log(e);
      }
    },
    stickyScrollChecker() {
      try {
        if (!this.scrollTrigger) return null;
        if (!this.table)
          this.table = this.$refs.table || document.querySelector('.table');

        const optionalHeaderHeight =
          document.querySelector('header')?.scrollHeight || 0;
        const optionalScrollH = this.scrollBox
          ? this.scrollBox.offsetHeight
          : 0;
        const stickyH = Math.max(
          this.$refs.fixed.querySelector('.head-sticky.row')?.offsetHeight || 0,
          this.$refs.auto.querySelector('.head-sticky.row')?.offsetHeight || 0
        );
        const screenH = document.documentElement.clientHeight;
        const scrollYTotal = window.pageYOffset + screenH;
        const tableTriggerTop =
          window.pageYOffset +
          this.table.getBoundingClientRect().top +
          stickyH +
          optionalScrollH;
        const topPos =
          window.pageYOffset +
          this.table.getBoundingClientRect().top +
          optionalScrollH;
        const computedOptions = window.getComputedStyle(this.table);
        const margBot = computedOptions?.marginBottom
          ? parseInt(computedOptions.marginBottom)
          : 0;

        const maxTopPos = this.table.clientHeight - margBot;

        if (tableTriggerTop < scrollYTotal) {
          this.scrollBox.style.top =
            Math.min(maxTopPos, scrollYTotal - topPos) + 'px';
        }
      } catch (e) {
        console.log(e);
      }
    },
    checkscrolledAuto(e) {
      try {
        if (!this.$refs.fixed) return null;
        if (e.target.scrollLeft) {
          this.$refs.fixed.classList.add('move');
        } else {
          this.$refs.fixed.classList.remove('move');
        }
      } catch (e) {
        console.log(e);
      }
    },
    rowHeightChecker() {
      try {
        const fixedRows = this.$refs?.fixed?.children
          ? Array.from(this.$refs.fixed.querySelectorAll('.row'))
          : [];
        const autoRows = this.$refs?.auto?.children
          ? Array.from(this.$refs.auto.querySelectorAll('.row'))
          : [];
        if (fixedRows.length != autoRows.length) {
          console.error(
            'Неравнозначное количество строк',
            fixedRows.length,
            autoRows.length
          );
        }
        fixedRows.forEach((item, i) => {
          const val = item.scrollHeight;
          const val2 = autoRows[i].scrollHeight;
          const maxVal = Math.max(val, val2);
          item.style.minHeight = maxVal + 'px';
          autoRows[i].style.minHeight = maxVal + 'px';
        });
      } catch (e) {
        console.log(e);
      }
    },
    createStickyScroll() {
      try {
        const totalW = this.$refs.auto?.scrollWidth || 0;
        const visibleW = this.$refs.auto?.clientWidth || 0; // Здесь меняем offsetWidth на clientWidth

        if (!this.scrollBox || !this.scrollTrigger) {
          if (visibleW < totalW) {
            let scrollBox = document.createElement('div');
            scrollBox.classList.add('scroll-box');
            let scrollTrigger = document.createElement('div');
            scrollTrigger.classList.add('scroll-trigger');
            scrollBox.append(scrollTrigger);
            this.$refs.table.append(scrollBox);
            this.$refs.table.classList.add('--scroll');
            this.scrollBox = scrollBox;
            this.scrollTrigger = scrollTrigger;

            // Правильное задание ширины контейнера и ползунка
            this.scrollBox.style.width = visibleW + 'px';
            const triggerWidth = (visibleW / totalW) * visibleW;
            scrollTrigger.style.width = triggerWidth + 'px';
          }
        } else {
          // Правильное обновление ширины ползунка при изменении размеров окна
          this.scrollBox.style.width = visibleW + 'px';
          const triggerWidth = (visibleW / totalW) * visibleW;
          this.scrollTrigger.style.width = triggerWidth + 'px';
        }
      } catch (e) {
        console.log(e);
      }
    },
    calculateScroleMove(pos, maxpos) {
      const scrollPercentage = (pos / maxpos) * 100;
      const newScrollLeft =
        (scrollPercentage / 100) *
        (this.$refs.auto.scrollWidth - this.$refs.auto.offsetWidth);
      return newScrollLeft;
    },
    mousedown(e) {
      try {
        e.preventDefault();
        let startX = e.clientX;
        const totalW = this.scrollBox.offsetWidth || 0;
        const visibleW = this.scrollTrigger.offsetWidth || 0;
        const maxScrollLeft = totalW - visibleW;

        const onMouseMove = (e) => {
          const deltaX = e.clientX - startX;
          startX = e.clientX;
          const leftPos = this.scrollTrigger?.style?.left
            ? parseInt(this.scrollTrigger.style.left)
            : 0;
          const newTriggerLeft = Math.min(
            maxScrollLeft,
            Math.max(0, leftPos + deltaX)
          );
          this.scrollTrigger.style.left = newTriggerLeft + 'px';
          this.$refs.auto.scrollLeft = this.calculateScroleMove(
            newTriggerLeft,
            maxScrollLeft
          );
        };

        const onMouseUp = () => {
          document.removeEventListener('mousemove', onMouseMove);
          document.removeEventListener('mouseup', onMouseUp);
        };

        document.addEventListener('mousemove', onMouseMove);
        document.addEventListener('mouseup', onMouseUp);
      } catch (e) {
        console.log(e);
      }
    },
    touchstart(e) {
      try {
        e.preventDefault();
        let startX = e.targetTouches[0].clientX;
        const totalW = this.scrollBox.offsetWidth || 0;
        const visibleW = this.scrollTrigger.offsetWidth || 0;
        const maxScrollLeft = totalW - visibleW;

        const onMouseMove = (e) => {
          const deltaX = e.targetTouches[0].clientX - startX;
          startX = e.targetTouches[0].clientX;
          const leftPos = this.scrollTrigger?.style?.left
            ? parseInt(this.scrollTrigger.style.left)
            : 0;
          const newTriggerLeft = Math.min(
            maxScrollLeft,
            Math.max(0, leftPos + deltaX)
          );
          this.scrollTrigger.style.left = newTriggerLeft + 'px';
          this.$refs.auto.scrollLeft = this.calculateScroleMove(
            newTriggerLeft,
            maxScrollLeft
          );
        };

        const onMouseUp = () => {
          document.removeEventListener('touchmove', onMouseMove);
          document.removeEventListener('touchend', onMouseUp);
        };

        document.addEventListener('touchmove', onMouseMove);
        document.addEventListener('touchend', onMouseUp);
      } catch (e) {
        console.log(e);
      }
    },
    scrollGorizontalMove(direction) {
      const val = 5;
      const currentLeftPos = this.scrollTrigger?.style?.left
        ? parseInt(this.scrollTrigger.style.left)
        : 0;
      if (direction) {
        const maxLeftPos =
          this.scrollBox.offsetWidth - this.scrollTrigger.offsetWidth;
        const newLeftPos = Math.min(maxLeftPos, currentLeftPos + val);
        this.scrollTrigger.style.left = newLeftPos + 'px';
        this.$refs.auto.scrollLeft = this.calculateScroleMove(
          newLeftPos,
          maxLeftPos
        );
      } else {
        const maxLeftPos = 0;
        const newLeftPos = Math.max(maxLeftPos, currentLeftPos - val);
        this.scrollTrigger.style.left = newLeftPos + 'px';
        this.$refs.auto.scrollLeft = this.calculateScroleMove(
          newLeftPos,
          this.scrollBox.offsetWidth - this.scrollTrigger.offsetWidth
        );
      }
    },
    keyDown({ keyCode }) {
      const right = 39;
      const left = 37;
      if (keyCode == right) this.scrollGorizontalMove(1);
      if (keyCode == left) this.scrollGorizontalMove(0);
    },
  },
  mounted() {
    this.currentScreenWidth = document.documentElement.offsetWidth;
    this.rowHeightChecker();
    this.createStickyScroll();
    this.stickyChecker();
    this.stickyScrollChecker();
    window.addEventListener('resize', this.scopeResize);
    window.addEventListener('scroll', this.scopeScroll);
    if (this.$refs.auto)
      this.$refs.auto.addEventListener('scroll', this.checkscrolledAuto);
    if (this.scrollTrigger) {
      this.scrollTrigger.addEventListener('mousedown', this.mousedown);
      this.scrollTrigger.addEventListener('touchstart', this.touchstart);
    }
    document.addEventListener('keydown', this.keyDown);
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.scopeScroll);
    window.removeEventListener('resize', this.scopeResize);
    if (this.scrollTrigger) {
      this.scrollTrigger.removeEventListener('mousedown', this.mousedown);
      this.scrollTrigger.removeEventListener('touchstart', this.touchstart);
    }

    if (this.$refs.auto)
      this.$refs.auto.removeEventListener('scroll', this.checkscrolledAuto);
    document.removeEventListener('keydown', this.keyDown);
  },
};
</script>
<style scoped lang="scss">
.table {
  display: flex;
  width: 100%;
  margin: 25px 0;
  position: relative;
  &.--scroll {
    padding-bottom: 25px;
    ::v-deep(.scroll-box) {
      height: 25px;
      background: #ffcd3821;
      position: absolute;
      top: calc(100% - 25px);
      right: 0;
      .scroll-trigger {
        position: relative;
        height: 100%;
        transition: width 0.2s;
        background: #ffcd38bb;
        cursor: pointer;
        transition: background 0.2s;
        &:active {
          background: #ffce38;
        }
      }
    }
  }
  .fixed {
    flex-shrink: 0;
    width: 300px;
    border-right: 2px solid transparent;
    transition: border-color 0.2s;
    &.move {
      border-color: #00cffa;
    }
    .row {
      & > div {
        &:nth-child(2) {
          flex-grow: 1;
        }
      }
    }
  }
  .auto {
    overflow: hidden;
    flex-grow: 1;
    position: relative;

    .row {
      & > div {
        &:nth-child(1),
        &:nth-child(2) {
          width: 100px;
        }
        &:nth-child(3) {
          width: 200px;
        }
        &:nth-child(4) {
          width: 150px;
        }
        &:nth-child(5) {
          width: 100px;
        }
        &:nth-child(6) {
          width: 200px;
        }
      }
    }
  }
  .head-sticky {
    color: #020509;
    font-weight: bold;
    z-index: 1;
    position: relative;
    &.move {
      & > div {
        border-bottom: 2px solid #00cffa;
      }
    }
    & > div {
      background: #ffce38;
      border-bottom: 2px solid transparent;
      transition: border-color 0.2s;
    }
  }
  .row {
    display: flex;
    width: 100%;
    & > div {
      padding: 5px 10px;
      text-align: left;
      flex-shrink: 0;
    }
  }
}
</style>
