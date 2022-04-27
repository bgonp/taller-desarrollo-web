---
clicks: 5
---

# NodeJS

<div grid="~ cols-2 gap-4">
<div>

- Entornos de ejecución
- ¿Qué es __NodeJS__?

<div v-click="1">

<hr />

- 📦 Empaquetar

</div>
<div v-click="2">

- 🗜 Minificar

</div>
<div v-click="4">

- 💬 Parsear

</div>

</div>
<div>

<div v-click-hide="2">

<img v-click="1" src="/assets/bundle.png">

</div>

<div v-click-hide="4" class="code-block">
<div v-click="2">

```javascript
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

</div>
<div v-click="3">

```javascript
async function a(t){const o=t.cp,c=t.ct,
n=(t.t-b(o))*c(c);await d(n)?e():f()}
```

</div>
</div>

<div v-click="4" class="code-block">

```javascript
foo ??= 2
```

<div v-click="5">

```javascript
var _a;
(_a = a) !== null && _a !== void 0 ? _a : a = 2;
```

</div>

</div>

</div>
</div>

<style>
	.code-block {
		position: absolute;
		right: 5%;
		top: 20%;
		width: 45%;
	}
	hr {
		opacity: 0.5;
		margin: 24px 24px 24px 0;
	}
</style>
