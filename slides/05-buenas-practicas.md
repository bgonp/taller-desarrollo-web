# Buenas prácticas

<div grid="~ cols-2 gap-4">
<div>

<v-click>

- 👷 Código escalable y mantenible
- 💪 Principios SOLID
- 💬 Clean Code
- 🏗 Patrones de diseño

</v-click>

<v-click>

> 👩‍🦰 Escribe para personas,<br>🤖 no para máquinas

</v-click>

</div>
<div>

<v-click>

```javascript
async function whatDoIDo(foo) {
	if (await pmnt((foo.t - ds(foo.cp)) * tx(foo.ct) ok();
	else nook();
}
```

</v-click>

<v-click>

```js {all|2-4|6-8|10|12-13|1}
async function whatDoIDo(foo) {
	const coupon = foo.cp;
	const country = foo.ct;
	const subtotal = foo.t

	const discount = getDiscountByCoupon(coupon);
	const taxes = getTaxesByCountry(country);
	const total = (subtotal - discount) * taxes;
	
	const paymentComplete = await redirectToPayment(total);

	if (paymentComplete) notifySuccess();
	else notifyError();
}
```

</v-click>

<v-click>

```javascript {1|all}
async function processOrder(order) {
	const coupon = order.cp;
	const country = order.ct;
	const subtotal = order.t

	const discount = getDiscountByCoupon(coupon);
	const taxes = getTaxesByCountry(country);
	const total = (subtotal - discount) * taxes;
	
	const paymentComplete = await redirectToPayment(total);

	if (paymentComplete) notifySuccess();
	else notifyError();
}
```

</v-click>

<v-click>

```javascript
async function whatDoIDo(foo) {
	const { cp: coupon, ct: country, t: total } = foo;
	var discount, taxes, finalPrice = total;
	if (!coupon) {
		discount = 0;
	} else if (coupon === 'OFFER5') {
		discount = 5;
	} else if (coupon === 'DISCOUNT10') {
		discount = 10;
	} else if (coupon === 'LILOFFER') {
		discount = 2;
	} else {
		discount = 0;
	}
	finalPrice -= discount;
	if (country === 'ES') {
		taxes = 1.21;
	} else if (country === 'AN') {
		taxes = 1.10;
	} else if (country === 'AU') {
		taxes = 1.20;
	} else if (country === 'FR') {
		taxes = 1.26;
	} else {
		taxes = 1;
	}
	finalPrice *= taxes;
	const paymentComplete = await redirectToPayment(finalPrice);
	if (paymentComplete) notifySuccess();
	else notifyError();
}
```

</v-click>

</div>
</div>

<style>
  h1 {
    margin-bottom: 22px!important;
  }
  .slidev-layout li {
    font-size: 22px;
    list-style: none;
    margin: 0;
    padding: 0;
  }
  .slidev-layout blockquote {
    margin: 24px 0 0 0;
    padding: 16px 24px;
    width: 85%;
  }
  .slidev-layout blockquote p {
    font-size: 22px;
    line-height: 1.5;
  }
  .slidev-code {
    position: fixed;
    top: 5%;
    right: 3%;
    width: 50%;
    height: 88%!important;
    font-size: 13px!important;
    letter-spacing: -0.5px;
  }
</style>
