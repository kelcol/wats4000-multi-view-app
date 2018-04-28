<template>
  <div class="Survey">
    <ol class="breadcrumb">
      <li class="breadcrumb-item">
        <router-link to="/">Home</router-link>
      </li>
      <li class="breadcrumb-item active">
        Survey
      </li>
    </ol>

    <div class="form-container container card bg-warning text-white mb-3">
      <h1 class="card-header">New Member Survey</h1>
      <p class="card-title">Please complete the new member survey.</p>

      <form class="card-body" v-on:submit.prevent="validateForm">
        <!--TODO: Work on error messaging:
      - Set timeout
      - Validate and alert for individual fields
      - Use all bootstrap styling -->
        <p v-show="showError" class="error alert alert-dismissible alert-danger">Dag! You broke it!</p>

        <fieldset class="form-group">
<legend for="q1">Q1: How long have you been building websites?</legend> 
          <div class="form-check">
            <label class="form-check-label" v-for="time in timeOptions">
              <ol>
                <li>
                  <input class="form-check-input" type="radio" v-model="q1" v-bind:value="time.value"> {{ time.text }}
                </li>
              </ol>
            </label>
          </div>
        </fieldset>










 

        <!--TODO: Make vertical -->
        <fieldset class="form-group">
          <legend for="q2">Q2: What languages interest you the most?</legend>
          <div class="form-check">
            <label class="form-check-label" v-for="language in languageOptions">
              <ol>
                <li>
                  <input class="form-check-input" type="checkbox" v-model="q2" v-bind:value="language.value"> {{ language.text }}
                </li>
              </ol>
            </label>
          </div>
        </fieldset>

        <fieldset class="form-group">
          <legend for="q3">Q3: What other topics interest you?</legend>
          <div class="form-check">
            <label class="form-check-label" v-for="topic in topicOptions">
              <ol>
                <li>
                  <input class="form-check-input" type="checkbox" v-model="q3" v-bind:value="topic.value"> {{ topic.text }}
                </li>
              </ol>
            </label>
          </div>
        </fieldset>


        <div class="form-group">
          <legend for="q4">Q4: What kinds of websites would you like to build someday?</legend>
          <textarea class="form-control" id="q4" rows="3" placeholder="Type your response here." v-model="q4"></textarea>
        </div>

        <div class="form-group"></div>


        <div class="form-group">
          <legend for="q5">Q5: Spaces or tabs?</legend>
          <select class="form-control" id="q5" v-model="q5">
            <!--TODO: Disable top option -->
            <option class="text-muted" value="">Select your preference.</option>
            <option value="spaces">Spaces</option>
            <option value="tabs">Tabs</option>
          </select>
        </div>

        <p>
          <input class="btn btn-primary" type="submit" value="Submit">
        </p>
      </form>

    </div>
  </div>

</template>



<script>
export default {
  name: 'Survey',
  data () {
    return {
      showError: false,
      q1: '',
      q2: [],
      q3: [],
      q4: '',
      q5: '',
      languageOptions: [
        {
            text: 'JavaScript',
            value: 'js'
        },
        {
            text: 'Python',
            value: 'py'
        },
        {
            text: 'Ruby',
            value: 'ruby'
        },
        {
            text: 'Java',
            value: 'java'
        },
        {
            text: 'PHP',
            value: 'php'
        }
      ],
      topicOptions: [
        {
            text: 'Accessibility',
            value: 'axe'
        },
        {
            text: 'Experience Design',
            value: 'ux'
        },
        {
            text: 'Operations',
            value: 'ops'
        },
        {
            text: 'Search Engine Optimization',
            value: 'seo'
        },
        {
            text: 'Multimedia',
            value: 'media'
        }
      ],
      timeOptions: [
        {
          text: '0-6 months',
          value: 'g1'
        },
        {
          text: '6 months to 1 year',
          value: 'g2'
        },
        {
          text: '1-2 years',
          value: 'g3'
        },
        {
          text: '3-5 years',
          value: 'g4'
        },
        {
          text: '5-10 years',
          value: 'g5'
        },
        {
          text: '10-15 years',
          value: 'g6'
        },
        {
          text: '15+ years',
          value: 'g7'
        }
      ]
    }
  },
  methods: {
    // TODO: validate each field individually through types or conditions
    validateForm: function () {
      if ((this.q1 != '') && 
      (this.q2.length > 0) && 
      (this.q3.length > 0) && 
      (this.q4 != '') &&
      (this.q5 != '')) {
        console.log('Form is valid');
        this.$router.push('Secret');
      } else {
        console.log('Form is not valid');
        this.showError = true;        
      }
    }
  }
}
</script>

