<template>
  <BaseCard>
    <form>
      <div>
        <label for="">Name</label>
        <input type="text" v-model="newTargetName" />
      </div>
      <div>
        <label for="">Current club</label>
        <input type="text" v-model="newTargetClub" />
      </div>
      <div>
        <label for="">Current value (mln €)</label>
        <input type="text" v-model="newTargetValue" />
      </div>
      <div>
        <label for="">Transfermarkt profile</label>
        <input type="text" v-model="newTargetProfile" />
      </div>
      <BaseButton class="submit-target" @click.prevent="saveNewTarget">
        Add to targets list
      </BaseButton>
    </form>
  </BaseCard>
  <teleport to="body"
    ><ErrorMessage v-if="errorMessageOpen" @close-error-modal="closeErrorModal">
    </ErrorMessage>
  </teleport>
</template>

<script>
import BaseCard from './BaseCard.vue';
import BaseButton from './BaseButton.vue';
import ErrorMessage from './ErrorMessage.vue';

export default {
  data() {
    return {
      newTargetName: '',
      newTargetClub: '',
      newTargetValue: '',
      newTargetProfile: '',
      errorMessageOpen: false,
    };
  },
  components: { BaseCard, BaseButton, ErrorMessage },
  methods: {
    saveNewTarget() {
      if (
        !this.newTargetName ||
        !this.newTargetClub ||
        !this.newTargetValue ||
        !this.newTargetProfile
      ) {
        this.errorMessageOpen = true;
        return;
      }
      this.$emit(
        'save-new-target',
        this.newTargetName,
        this.newTargetClub,
        this.newTargetValue,
        this.newTargetProfile
      );
      this.newTargetName = '';
      this.newTargetClub = '';
      this.newTargetValue = '';
      this.newTargetProfile = '';
    },
    closeErrorModal() {
      this.errorMessageOpen = false;
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

form div {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  gap: 2rem;
  align-items: center;
}

label {
  width: 20%;
}

input {
  font-size: 1.5rem;
  line-height: 2.5rem;
  border-radius: 25px;
  padding-left: 10px;
  width: 70%;
}

.submit-target {
  width: 50%;
  margin: 0 auto;
}
</style>