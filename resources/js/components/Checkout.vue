<template>
  <div>
    <div class="container checkoutBox">
      <div class="row">
        <div class="col-lg-8 col-md-8 col-sm-7 col-xs-12">
          <div class="box">
            <h3 class="box-title">Product in your cart</h3>
            <div class="plan-selection" v-for="item in items" :key="item.id">
              <div class="plan-data" v-if="item.name && item.image_name">
                <!-- <input
                  id="question1"
                  name="question"
                  type="radio"
                  class="with-font"
                  value="sel"
                /> -->
                <label for="question1">{{ item.name }}</label>
                <p class="plan-text">Quantity : {{ item.quantity }}</p>
                <img v-bind:src="'/assets/images/product/' + item.image_name" alt="" height="100px" width="100px">
                <!-- <p>{{item.image_name}}</p> -->
                <span class="plan-price">Price : $ {{ item.sale_price }}</span>
              </div>
              
            </div>
            <div>
              <!--SHIPPING METHOD-->
              <div class="panel panel-info">
                <div class="panel-body">
                  <div class="form-group">
                    <div class="col-md-12">
                      <h4>Shipping Address</h4>
                    </div>
                  </div>
                  <div class="form-group">
                    <div class="col-md-12"><strong>Country:</strong></div>
                    <div class="col-md-12">
                      <input
                        type="text"
                        class="form-control"
                        name="country"
                        value=""
                        v-model="country"
                      />
                    </div>
                  </div>
                  <div class="form-group">
                    <div class="col-md-6 col-xs-12">
                      <strong>First Name:</strong>
                      <input
                        type="text"
                        name="first_name"
                        v-model="firstName"
                        class="form-control"
                        value=""
                      />
                    </div>
                    <div class="span1"></div>
                    <div class="col-md-6 col-xs-12">
                      <strong>Last Name:</strong>
                      <input
                        type="text"
                        name="last_name"
                        class="form-control"
                        value=""
                        v-model="lastName"
                      />
                    </div>
                  </div>
                  <div class="form-group">
                    <div class="col-md-12"><strong>Address:</strong></div>
                    <div class="col-md-12">
                      <input
                        type="text"
                        name="address"
                        class="form-control"
                        value=""
                        v-model="address"
                      />
                    </div>
                  </div>
                  <div class="form-group">
                    <div class="col-md-12"><strong>City:</strong></div>
                    <div class="col-md-12">
                      <input
                        type="text"
                        name="city"
                        class="form-control"
                        value=""
                        v-model="city"
                      />
                    </div>
                  </div>
                  <div class="form-group">
                    <div class="col-md-12"><strong>State:</strong></div>
                    <div class="col-md-12">
                      <input
                        type="text"
                        name="state"
                        class="form-control"
                        value=""
                        v-model="state"
                      />
                    </div>
                  </div>
                  <div class="form-group">
                    <div class="col-md-12">
                      <strong>Zip / Postal Code:</strong>
                    </div>
                    <div class="col-md-12">
                      <input
                        type="text"
                        name="zip_code"
                        class="form-control"
                        value=""
                        v-model="zipCode"
                      />
                    </div>
                  </div>
                  <div class="form-group">
                    <div class="col-md-12"><strong>Phone Number:</strong></div>
                    <div class="col-md-12">
                      <input
                        type="text"
                        name="phone_number"
                        class="form-control"
                        value=""
                        v-model="phone"
                      />
                    </div>
                  </div>
                  <div class="form-group">
                    <div class="col-md-12"><strong>Email Address:</strong></div>
                    <div class="col-md-12">
                      <input
                        type="text"
                        name="email_address"
                        class="form-control"
                        value=""
                        v-model="email"
                      />
                    </div>
                  </div>
                </div>
              </div>
              <!--SHIPPING METHOD END-->
              <hr />
              <!--CREDIT CART PAYMENT-->
              <div class="panel panel-info">
                <h4>Secure Payment</h4>
                <br />
                <div class="panel-body">
                  <div class="form-group">
                    <div class="col-md-12"><strong>Card Type:</strong></div>
                    <div class="col-md-12">
                      <select
                        id="CreditCardType"
                        name="CreditCardType"
                        class="form-control"
                        v-model="cardType"
                      >
                        <option value="5">Visa</option>
                        <option value="6">MasterCard</option>
                        <option value="7">American Express</option>
                        <option value="8">Discover</option>
                      </select>
                    </div>
                  </div>
                  <div class="form-group">
                    <div class="col-md-12">
                      <strong>Credit Card Number:</strong>
                    </div>
                    <div class="col-md-12">
                      <input
                        type="text"
                        class="form-control"
                        name="car_number"
                        value=""
                        v-model="cardNumber"
                      />
                    </div>
                  </div>
                  <div class="form-group">
                    <div class="col-md-12"><strong>Card CVV:</strong></div>
                    <div class="col-md-12">
                      <input
                        type="text"
                        class="form-control"
                        name="car_code"
                        value=""
                        v-model="cvv"
                      />
                    </div>
                  </div>
                  <div class="form-group">
                    <div class="col-md-12">
                      <strong>Expiration Date</strong>
                    </div>
                    <div class="col-lg-6 col-md-6 col-sm-6 col-xs-12">
                      <select
                        class="form-control"
                        name=""
                        v-model="expirationMonth"
                      >
                        <option value="">Month</option>
                        <option value="01">01</option>
                        <option value="02">02</option>
                        <option value="03">03</option>
                        <option value="04">04</option>
                        <option value="05">05</option>
                        <option value="06">06</option>
                        <option value="07">07</option>
                        <option value="08">08</option>
                        <option value="09">09</option>
                        <option value="10">10</option>
                        <option value="11">11</option>
                        <option value="12">12</option>
                      </select>
                    </div>
                    <div class="col-lg-6 col-md-6 col-sm-6 col-xs-12">
                      <select
                        class="form-control"
                        name=""
                        v-model="expirationYear"
                      >
                        <option value="">Year</option>
                        <option value="2015">2018</option>
                        <option value="2016">2019</option>
                        <option value="2017">2020</option>
                        <option value="2018">2021</option>
                        <option value="2019">2022</option>
                        <option value="2020">2023</option>
                        <option value="2021">2024</option>
                        <option value="2022">2025</option>
                        <option value="2023">2026</option>
                        <option value="2024">2027</option>
                        <option value="2025">2028</option>
                      </select>
                    </div>
                  </div>
                  <div class="form-group">
                    <div class="col-md-12">
                      <span>Pay secure using your credit card.</span>
                    </div>
                    <div class="col-md-12">
                      <ul class="cards">
                        <li class="visa hand">Visa</li>
                        <li class="mastercard hand">MasterCard</li>
                        <li class="amex hand">Amex</li>
                      </ul>
                      <div class="clearfix"></div>
                    </div>
                  </div>
                  <div class="form-group">
                    <div class="col-md-6 col-sm-6 col-xs-12">
                      <button
                        type="submit"
                        class="btn btn-primary btn-submit-fix"
                        v-on:click.prevent="getUserAddress()"
                      >
                        Place Order
                      </button>
                    </div>
                  </div>
                </div>
              </div>
              <!--CREDIT CART PAYMENT END-->
            </div>
          </div>
        </div>
        <div class="col-lg-4 col-md-4 col-sm-5 col-xs-12">
          <div class="widget">
            <h4 class="widget-title">Order Summary</h4>
            <div
              class="summary-block"
              v-for="summaryItem in items"
              :key="summaryItem.id"
            >
              <div class="summary-content" v-if="summaryItem.name">
                <div class="summary-head">
                  <h5 class="summary-title">{{ summaryItem.name }}</h5>
                </div>
                <div class="summary-price">
                  <p class="summary-text">$ {{ summaryItem.total }}</p>
                  <br />
                  <span class="summary-small-text pull-right">
                    Q&nbsp;:{{ summaryItem.quantity }} x P&nbsp;: $
                    {{ summaryItem.sale_price }}</span
                  >
                </div>
              </div>
            </div>
            <div class="summary-block">
              <div class="summary-content">
                <div class="summary-head">
                  <h5 class="summary-title">Total</h5>
                </div>
                <div class="summary-price">
                  <p class="summary-text">$ {{ items.totalAmount }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [],
      firstName: '',
      lastName: '',
      address: '',
      city: '',
      state: '',
      zipCode: '',
      email: '',
      phone: '',
      country: '',

      cardType: '',
      expirationMonth: '',
      expirationYear: '',
      cvv: '',
      cardNumber: '',
    };
  },
  methods: {
    async getCartItems() {
      let response = await axios.get('/checkout/get/items');
      this.items = response.data;
      console.log(this.items);
    },
    async getUserAddress() {
      if (
        this.firstName != '' &&
        this.address != '' &&
        this.cardNumber &&
        this.cvv
      ) {
        // Process payment
        let response = await axios.post('/process/user/payment', {
          'firstName': this.firstName,
          'lastName': this.lastName,
          'address': this.address,
          'city': this.city,
          'state': this.state,
          'zipCode': this.zipCode,
          'email': this.email,
          'phone': this.phone,
          'country': this.country,

          'cardType': this.cardType,
          'expirationMonth': this.expirationMonth,
          'expirationYear': this.expirationYear,
          'cvv': this.cvv,
          'cardNumber': this.cardNumber,
          'amount': this.items.totalAmount,
          'order' : this.items, 
        });
        if(response.data.success){
          this.$toastr.s(response.data.success);
        }else{
          this.$toastr.s(response.data.console.error);
        }

        setTimeout(()=>{
          window.location.href='/';
        },1000);
        
        console.log(response.data);
      } 
      else 
      {
        this.$toastr.e("User info incomplete");
      }
    },
  },
  created() {
    this.getCartItems();
  },
};
</script>