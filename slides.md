---
theme: seriph
title: Customer Portal Migration - Vue 2 to Vue 3
layout: cover
class: text-center
transition: slide-left
mdc: true
---

# Customer Portal Migration

## Vue 2 → Vue 3

<div class="text-xl mt-4 opacity-80">
Modernizing Our Frontend Architecture for Scalability & Performance
</div>


<div class="abs-bl m-6 flex gap-2 text-sm opacity-50">
  <span>2026</span>
  <span>·</span>
  <span>Frontend Engineering Team</span>
</div>

<style>
.slidev-layout {
  background: linear-gradient(135deg, #1a1a2e 0%, #16213e 40%, #0f3460 100%) !important;
  overflow: hidden;
}

/* Top-right Vue green glow */
.slidev-layout::before {
  content: '';
  position: absolute;
  top: -80px;
  right: -80px;
  width: 480px;
  height: 480px;
  background: radial-gradient(circle, rgba(66, 184, 131, 0.15) 0%, transparent 70%);
  pointer-events: none;
  z-index: 0;
}

/* Bottom-left Vue green glow */
.slidev-layout::after {
  content: '';
  position: absolute;
  bottom: -120px;
  left: -100px;
  width: 400px;
  height: 400px;
  background: radial-gradient(circle, rgba(66, 184, 131, 0.1) 0%, transparent 70%);
  pointer-events: none;
  z-index: 0;
}

/* Geometric accent line */
.geo-line {
  position: absolute;
  height: 1px;
  background: linear-gradient(90deg, transparent, rgba(66, 184, 131, 0.4), transparent);
  pointer-events: none;
  z-index: 0;
}

/* Diamond accents */
.geo-diamond {
  position: absolute;
  background: rgba(66, 184, 131, 0.25);
  transform: rotate(45deg);
  pointer-events: none;
  z-index: 0;
}

h1 {
  color: #fff !important;
  font-size: 3.2em !important;
  font-weight: 700 !important;
  letter-spacing: -0.02em;
  text-shadow: 0 2px 10px rgba(0,0,0,0.3);
  position: relative;
  z-index: 1;
}

h2 {
  background: linear-gradient(90deg, #42b883, #35d6a0);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  font-size: 1.8em !important;
  font-weight: 600 !important;
  letter-spacing: 0.05em;
  margin-top: 0.2em !important;
  position: relative;
  z-index: 1;
}
</style>

<!-- Geometric accent lines -->
<div class="geo-line" style="top: 25%; right: 40px; width: 240px;"></div>
<div class="geo-line" style="bottom: 33%; left: 60px; width: 160px;"></div>
<div class="geo-line" style="top: 15%; left: 10%; width: 100px; opacity: 0.5;"></div>

<!-- Diamond accents -->
<div class="geo-diamond" style="top: 80px; left: 25%; width: 12px; height: 12px;"></div>
<div class="geo-diamond" style="bottom: 100px; right: 30%; width: 8px; height: 8px; opacity: 0.6;"></div>
<div class="geo-diamond" style="top: 40%; right: 12%; width: 6px; height: 6px; opacity: 0.4;"></div>

<!--
Opening slide for the Customer Portal Migration presentation.
This covers the strategic move from Vue 2 to Vue 3, focusing on scalability and performance improvements.
-->

---
layout: two-cols
layoutClass: gap-8
transition: slide-left
---

# What Changed

A complete rewrite of the Customer Portal from legacy stack to modern Vue 3 ecosystem.

<div class="mt-4 text-sm">

| Category | Before | After |
|---|---|---|
| **Framework** | Nuxt 2 (Vue 2) | Vue 3 + Vite |
| **Language** | JavaScript | TypeScript |
| **API Style** | Options API + Pug | Composition API `<script setup>` |
| **State** | Vuex (single 32KB store) | TanStack Vue Query |
| **Styling** | Bootstrap + BootstrapVue | TailwindCSS |
| **Validation** | VeeValidate 2 | Vuelidate 2 |
| **Date Utils** | Moment.js | date-fns |
| **Testing** | None | Vitest + Storybook |
| **Monitoring** | None | Sentry |

</div>

::right::

<div class="mt-10 text-xs">

<div v-motion :initial="{ y: -20, opacity: 0 }" :enter="{ y: 0, opacity: 1, transition: { delay: 300 } }">

**Component Architecture**

</div>

````md magic-move {at: 1}
```text
// Before — Atomic Design (Vue 2)
components/
├── atoms/ (12)
│   AppAlert, AppBadge, AppButton,
│   AppChip, AppDatepicker, AppInput,
│   AppModal, AppSheet, AppStepper ...
├── molecules/ (6)
│   AppAioPayElement, AppOrderSummary,
│   AppDeliveryInformation ...
└── template/ (7)
    AppPayment, AppTracking,
    AppSchedule, AppSpecialOrders ...
```
```text
// After — Feature-based (Vue 3)
components/
├── primitives/ (26)
│   Alert, Badge, Button, Card,
│   Input, Modal, Select, Sheet,
│   Toast, Tooltip, Stepper ...
├── compositions/ (9)
│   Payment/, DeliveryTracking/,
│   DeliverySchedule/, OrderSummary/,
│   ReviewAddOns/, SpecialOrder/ ...
└── layouts/ (2)
    DefaultLayout, BlankLayout
```
````

<div v-click="2" v-motion :initial="{ y: 15, opacity: 0 }" :enter="{ y: 0, opacity: 1, transition: { delay: 200 } }">

**New Patterns Introduced**

</div>

<v-clicks at="3">

- Composables (`usePayment`, `useGoogleMap`, `useToast`)
- Typed API layer with request/response interfaces
- Vue Query hooks for server state & caching
- Custom directives (`v-safe-html`)
- Error tracking with Sentry

</v-clicks>

</div>

<style>
h1 {
  background: linear-gradient(90deg, #42b883, #35d6a0);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

table {
  font-size: 0.75em !important;
}

th {
  background: rgba(66, 184, 131, 0.1) !important;
}
</style>

<!--
Key takeaway: This wasn't just a version bump — it was a full architectural modernization.
JavaScript to TypeScript, Options API to Composition API, Vuex to Vue Query, Bootstrap to Tailwind.
-->

---
layout: two-cols
layoutClass: gap-8
transition: slide-left
---

# Why Migrate?

<div class="text-xs mt-2 opacity-70 mb-4">The legacy stack had reached its limits</div>

<div class="text-sm">

<div v-click="1" class="flex items-start gap-2 mb-3">
  <span class="text-red-400 text-base mt-0.5">&#x2718;</span>
  <div><strong>Vue 2 & Nuxt 2 — End of Life</strong><br><span class="opacity-70">No security patches, no ecosystem updates</span></div>
</div>

<div v-click="2" class="flex items-start gap-2 mb-3">
  <span class="text-red-400 text-base mt-0.5">&#x2718;</span>
  <div><strong>No TypeScript</strong><br><span class="opacity-70">Runtime bugs, no IDE type safety, harder refactoring</span></div>
</div>

<div v-click="3" class="flex items-start gap-2 mb-3">
  <span class="text-red-400 text-base mt-0.5">&#x2718;</span>
  <div><strong>Monolithic Vuex Store (32KB single file)</strong><br><span class="opacity-70">Tightly coupled state, difficult to maintain & debug</span></div>
</div>

<div v-click="4" class="flex items-start gap-2 mb-3">
  <span class="text-red-400 text-base mt-0.5">&#x2718;</span>
  <div><strong>Zero Test Coverage & No Monitoring</strong><br><span class="opacity-70">Blind deployments, no visibility into production errors</span></div>
</div>

<div v-click="5" class="flex items-start gap-2 mb-3">
  <span class="text-red-400 text-base mt-0.5">&#x2718;</span>
  <div><strong>Heavy Dependencies</strong><br><span class="opacity-70">Moment.js, BootstrapVue — large bundles, discontinued libraries</span></div>
</div>

</div>

::right::

<div class="mt-10 text-sm">

<div v-click="6" class="mb-4">
  <div class="text-base font-semibold text-green-400 mb-3">Business Value Delivered</div>
</div>

<div v-click="7" class="flex items-start gap-2 mb-3">
  <span class="text-green-400 text-base mt-0.5">&#x2714;</span>
  <div><strong>Security & Compliance</strong><br><span class="opacity-70">Actively maintained framework with regular patches</span></div>
</div>

<div v-click="8" class="flex items-start gap-2 mb-3">
  <span class="text-green-400 text-base mt-0.5">&#x2714;</span>
  <div><strong>Faster Development Cycles</strong><br><span class="opacity-70">TypeScript + Composition API = fewer bugs, faster iteration</span></div>
</div>

<div v-click="9" class="flex items-start gap-2 mb-3">
  <span class="text-green-400 text-base mt-0.5">&#x2714;</span>
  <div><strong>Production Reliability</strong><br><span class="opacity-70">Vitest + Storybook + Sentry = confidence in every release</span></div>
</div>

<div v-click="10" class="flex items-start gap-2 mb-3">
  <span class="text-green-400 text-base mt-0.5">&#x2714;</span>
  <div><strong>Performance Gains</strong><br><span class="opacity-70">Vite builds, tree-shakeable deps, smaller runtime</span></div>
</div>

<div v-click="11" class="flex items-start gap-2 mb-3">
  <span class="text-green-400 text-base mt-0.5">&#x2714;</span>
  <div><strong>Future-Proof & Scalable</strong><br><span class="opacity-70">Modern stack that grows with the product and attracts talent</span></div>
</div>

</div>

<style>
h1 {
  background: linear-gradient(90deg, #42b883, #35d6a0);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

/* Override default v-click fade with slide-in animation */
.slidev-vclick-target {
  transition: none !important;
}

.slidev-vclick-target.slidev-vclick-hidden {
  opacity: 0 !important;
  transform: translateX(-20px);
}

.slidev-vclick-target:not(.slidev-vclick-hidden) {
  animation: slideIn 0.4s cubic-bezier(0.25, 1, 0.5, 1) forwards;
}

@keyframes slideIn {
  0% { opacity: 0; transform: translateX(-20px); }
  100% { opacity: 1; transform: translateX(0); }
}
</style>

<!--
The migration wasn't optional — Vue 2 hit EOL Dec 2023. No security patches, no BootstrapVue support for Vue 3.
The 32KB monolithic Vuex store was a maintenance nightmare. Zero tests meant every deploy was a gamble.
-->

---
transition: slide-left
---

# Who Is Impacted?

<div class="grid grid-cols-3 gap-6 mt-6">

<div v-click="1" class="border border-gray-600 rounded-lg p-4">
  <carbon-user-multiple class="text-2xl mb-2 text-green-400" />
  <div class="text-base font-semibold text-green-400 mb-2">Customers</div>
  <div class="text-xs opacity-80 leading-relaxed">
    <div class="mb-1">&#x2022; Faster page loads (Vite + tree-shaking)</div>
    <div class="mb-1">&#x2022; Smoother micro-interactions & transitions</div>
    <div class="mb-1">&#x2022; More responsive & intuitive UI</div>
    <div>&#x2022; Fewer bugs reaching production</div>
  </div>
</div>

<div v-click="2" class="border border-gray-600 rounded-lg p-4">
  <carbon-code class="text-2xl mb-2 text-blue-400" />
  <div class="text-base font-semibold text-blue-400 mb-2">Frontend Team</div>
  <div class="text-xs opacity-80 leading-relaxed">
    <div class="mb-1">&#x2022; Vite + TypeScript dev workflow</div>
    <div class="mb-1">&#x2022; ESLint + Prettier for code quality</div>
    <div class="mb-1">&#x2022; Husky + lint-staged pre-commit hooks</div>
    <div class="mb-1">&#x2022; Commitlint for conventional commits</div>
    <div>&#x2022; Vitest, Storybook & Sentry</div>
  </div>
</div>

<div v-click="3" class="border border-gray-600 rounded-lg p-4">
  <carbon-product class="text-2xl mb-2 text-purple-400" />
  <div class="text-base font-semibold text-purple-400 mb-2">QA & Product Team</div>
  <div class="text-xs opacity-80 leading-relaxed">
    <div class="mb-1">&#x2022; Unit tests catch bugs before QA</div>
    <div class="mb-1">&#x2022; Storybook for visual component review</div>
    <div class="mb-1">&#x2022; Faster, more confident releases</div>
    <div>&#x2022; Less regression, shorter QA cycles</div>
  </div>
</div>

</div>

<div v-click="4" class="mt-6 border border-green-800 bg-green-900 bg-opacity-20 rounded-lg p-4 text-sm">
  <span class="text-green-400 font-semibold">Key point:</span> <span class="opacity-80">Seamless transition — same API contracts, same features, modernized frontend only.</span>
</div>

<style>
h1 {
  background: linear-gradient(90deg, #42b883, #35d6a0);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.slidev-vclick-target {
  transition: none !important;
}

.slidev-vclick-target.slidev-vclick-hidden {
  opacity: 0 !important;
  transform: translateY(15px);
}

.slidev-vclick-target:not(.slidev-vclick-hidden) {
  animation: slideUp 0.4s cubic-bezier(0.25, 1, 0.5, 1) forwards;
}

@keyframes slideUp {
  0% { opacity: 0; transform: translateY(15px); }
  100% { opacity: 1; transform: translateY(0); }
}
</style>

<!--
The migration is frontend-only. API contracts with the Laravel backend remain unchanged.
Customers get a faster, smoother experience. The frontend team gets modern tooling. Systems stay connected as before.
-->

---
transition: slide-left
---

# Where Does It Apply?

<div class="text-xs mt-1 opacity-70 mb-4">Every product area in the Customer Portal was migrated end-to-end</div>

<div class="grid grid-cols-2 gap-x-8 gap-y-2">

<div>

<div v-click="1" class="text-sm font-semibold text-green-400 mb-3">Customer Journey Flow</div>

<div class="flex flex-col gap-2 text-xs">

<div v-click="2" class="flex items-center gap-2">
  <div class="border border-amber-500 bg-amber-500 bg-opacity-10 rounded px-3 py-1.5 flex items-center gap-2 flex-1">
    <carbon-document class="text-amber-400" />
    <div><strong>Special Order</strong><span class="opacity-60 ml-1">— Quote review & approval</span></div>
  </div>
</div>

<div v-click="3" class="flex items-center gap-2">
  <div class="flow-line ml-4"></div>
</div>

<div v-click="3" class="flex items-center gap-2">
  <div class="border border-blue-500 bg-blue-500 bg-opacity-10 rounded px-3 py-1.5 flex items-center gap-2 flex-1">
    <carbon-shopping-cart class="text-blue-400" />
    <div><strong>Review Add-Ons</strong><span class="opacity-60 ml-1">— Addon selection & pricing</span></div>
  </div>
</div>

<div v-click="4" class="flex items-center gap-2">
  <div class="flow-line ml-4"></div>
</div>

<div v-click="4" class="flex items-center gap-2">
  <div class="border border-green-500 bg-green-500 bg-opacity-10 rounded px-3 py-1.5 flex items-center gap-2 flex-1">
    <carbon-wallet class="text-green-400" />
    <div><strong>Payment</strong><span class="opacity-60 ml-1">— Adyen (credit card & ACH)</span></div>
  </div>
</div>

<div v-click="5" class="flex items-center gap-2">
  <div class="flow-line ml-4"></div>
</div>

<div v-click="5" class="flex items-center gap-2">
  <div class="border border-purple-500 bg-purple-500 bg-opacity-10 rounded px-3 py-1.5 flex items-center gap-2 flex-1">
    <carbon-calendar class="text-purple-400" />
    <div><strong>Delivery Scheduling</strong><span class="opacity-60 ml-1">— Date & time selection</span></div>
  </div>
</div>

<div v-click="6" class="flex items-center gap-2">
  <div class="flow-line ml-4"></div>
</div>

<div v-click="6" class="flex items-center gap-2">
  <div class="border border-cyan-500 bg-cyan-500 bg-opacity-10 rounded px-3 py-1.5 flex items-center gap-2 flex-1">
    <carbon-delivery-truck class="text-cyan-400" />
    <div><strong>Delivery Tracking</strong><span class="opacity-60 ml-1">— Real-time map & status</span></div>
  </div>
</div>

</div>
</div>

<div>

<div v-click="7" class="text-sm font-semibold text-blue-400 mb-3">Systems & Integrations</div>

<div class="text-xs flex flex-col gap-2.5">

<div v-click="8" class="flex items-center gap-2.5">
  <carbon-api class="text-orange-400 text-base flex-shrink-0" />
  <div><strong>Laravel API</strong><span class="opacity-60 ml-1">— Same contracts, 4 API modules</span></div>
</div>

<div v-click="9" class="flex items-center gap-2.5">
  <carbon-flash class="text-yellow-400 text-base flex-shrink-0" />
  <div><strong>Laravel Echo + Socket.io</strong><span class="opacity-60 ml-1">— Real-time updates</span></div>
</div>

<div v-click="10" class="flex items-center gap-2.5">
  <carbon-purchase class="text-green-400 text-base flex-shrink-0" />
  <div><strong>Adyen Payment Gateway</strong><span class="opacity-60 ml-1">— Card & ACH</span></div>
</div>

<div v-click="11" class="flex items-center gap-2.5">
  <carbon-map class="text-blue-400 text-base flex-shrink-0" />
  <div><strong>Google Maps</strong><span class="opacity-60 ml-1">— Delivery tracking</span></div>
</div>

<div v-click="12" class="flex items-center gap-2.5">
  <carbon-warning-alt class="text-red-400 text-base flex-shrink-0" />
  <div><strong>Sentry</strong><span class="opacity-60 ml-1">— Error monitoring (new)</span></div>
</div>

</div>

<div v-click="13" class="mt-5 border border-blue-800 bg-blue-900 bg-opacity-20 rounded-lg p-3 text-xs">
  <span class="text-blue-400 font-semibold">Scope:</span> <span class="opacity-80">Single-page app — one route, step-based navigation driven by backend mode state.</span>
</div>

</div>

</div>

<style>
h1 {
  background: linear-gradient(90deg, #42b883, #35d6a0);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.slidev-vclick-target {
  transition: none !important;
}

.slidev-vclick-target.slidev-vclick-hidden {
  opacity: 0 !important;
  transform: translateX(-15px);
}

.slidev-vclick-target:not(.slidev-vclick-hidden) {
  animation: slideInLeft 0.35s cubic-bezier(0.25, 1, 0.5, 1) forwards;
}

@keyframes slideInLeft {
  0% { opacity: 0; transform: translateX(-15px); }
  100% { opacity: 1; transform: translateX(0); }
}

/* Animated dashed flow connector */
.flow-line {
  width: 2px;
  height: 14px;
  background: repeating-linear-gradient(
    to bottom,
    rgba(66, 184, 131, 0.6) 0px,
    rgba(66, 184, 131, 0.6) 3px,
    transparent 3px,
    transparent 6px
  );
  background-size: 2px 12px;
  animation: flowDash 0.8s linear infinite;
}

@keyframes flowDash {
  0% { background-position: 0 0; }
  100% { background-position: 0 12px; }
}
</style>

<!--
The app is a single-page, step-based customer portal. The flow is: Special Order → Review Add-Ons → Payment → Delivery Scheduling → Delivery Tracking.
Steps are conditionally shown based on backend mode state. All integrations preserved during migration.
-->

---
transition: slide-left
class: code-sm
---

# How: API Communication

<div class="text-xs opacity-70 mb-2">Same endpoint — click to see the transformation</div>

````md magic-move {lines: true}
```js
// Before — store/index.js (32KB single file)
export const actions = {
  async getAdyenPaymentMethods({ state }, payload) {
    const response = await this.$axios.get(
      'payment-customer/payment/aio-payment-methods',
      { params: { link: state.track, ...payload } }
    )
    return response
  },
}
// ❌ No types — payload and response are untyped
// ❌ No caching — every call hits the server
// ❌ No loading/error states — handled manually
// ❌ Buried in a 32KB monolithic store file
```
```ts
// After (1/3) — api/payment.ts
import { axiosInstance } from '@/plugins/axios'

interface GetPaymentMethodsRequest { link: string; amount?: number }
interface GetPaymentMethodsResponse { paymentMethods: PaymentMethod[] }

export async function getPaymentMethods(
  payload: GetPaymentMethodsRequest,
): Promise<AxiosResponse<GetPaymentMethodsResponse>> {
  return await axiosInstance.get<GetPaymentMethodsResponse>(
    'payment-customer/payment/aio-payment-methods',
    { params: payload },
  )
}
// ✅ Typed request & response — full autocomplete
// ✅ Standalone module — easy to find and maintain
```
```ts
// After (2/3) — composables/queries/usePaymentQueries.ts
import { useQuery } from '@tanstack/vue-query'
import { getPaymentMethods } from '@/api/payment'

export function usePaymentMethodsQuery(
  payload: MaybeRefOrGetter<GetPaymentMethodsRequest>,
) {
  return useQuery({
    queryKey: ['paymentMethods', payload],
    queryFn: async () => {
      const res = await getPaymentMethods(toValue(payload))
      return res.data
    },
    enabled: () => !!toValue(payload),
  })
}
// ✅ Automatic caching & deduplication
// ✅ Built-in loading, error & refetch states
```
```vue
<!-- After (3/3) — Payment.vue -->
<script setup lang="ts">
const route = useRoute()
// One line — fully typed, cached, reactive
const { data, isLoading, error } = usePaymentMethodsQuery({
  link: route.query.link as string,
})
</script>
<template>
  <Spinner v-if="isLoading" />
  <Alert v-else-if="error" color="danger">{{ error }}</Alert>
  <PaymentForm v-else :methods="data.paymentMethods" />
</template>
<!-- ✅ Clean separation: API → Query → Component -->
<!-- ✅ Loading & error states handled declaratively -->
```
````

<div v-click class="mt-2 text-xs border border-green-800 bg-green-900 bg-opacity-15 rounded p-2">
  <carbon-checkmark-filled class="text-green-400 inline" /> 4 API modules (<code>deliveryRoute</code>, <code>deliverySchedule</code>, <code>payment</code>, <code>specialOrder</code>) — all follow this same pattern.
</div>

<style>
h1 {
  background: linear-gradient(90deg, #42b883, #35d6a0);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.code-sm :deep(pre), .code-sm :deep(code) {
  font-size: 0.65em !important;
  line-height: 1.35 !important;
}
</style>

<!--
The API layer went from untyped calls scattered in a 32KB Vuex store to dedicated typed modules.
Vue Query adds caching, deduplication, background refetching, and loading/error states for free.
-->

---
transition: slide-left
class: code-sm
---

# How: Composables

<div class="text-xs opacity-70 mb-2">From scattered component logic to reusable, testable composables</div>

````md magic-move {lines: true}
```js
// Before — Payment logic inside component (Options API)
export default {
  name: 'AppPayment',
  computed: {
    ...mapGetters({ currentRoute: 'currentRoute', steps: 'steps' }),
    amountPayment() {
      return this.currentRoute.data.is_partial_payment === 1
        ? this.currentRoute.data.current_payment
        : this.currentBalanceDue
    },
  },
  methods: {
    ...mapActions({ postPaymentQuote: 'postPaymentQuote' }),
    ...mapMutations({ setInitialLoading: 'setInitialLoadingMutation' }),
    async onPayment({ paymentMethod }) {
      this.setInitialLoading(true)
      // ...business logic mixed with UI concerns
    },
  },
}
// ❌ Logic tied to this component — can't reuse
// ❌ mapGetters/mapActions boilerplate
// ❌ Hard to test — needs full Vuex store mock
```
```ts
// After (1/2) — composables/domain/usePayment.ts
const isProcessingPayment = ref(false) // module-level shared state

export const usePayment = () => {
  const { paymentData } = useDeliveryRouteQuery()

  const isPartialPayment = computed((): boolean =>
    paymentData.value?.data.is_partial_payment === 1
  )
  const amountPayment = computed((): number =>
    isPartialPayment.value
      ? paymentData.value?.data.current_payment ?? 0
      : balanceDue.value
  )
  const onProcessPayment = async ({ paymentMethod }) => {
    await withReloadPrevention(async () => {
      showLoading()
      // ...business logic only, no UI concerns
    })
  }
  return { isProcessingPayment, isPartialPayment,
    amountPayment, onProcessPayment }
}
// ✅ Reusable across any component
// ✅ Testable in isolation — no store needed
```
```vue
<!-- After (2/2) — Used in Payment.vue -->
<script setup lang="ts">
const { isPartialPayment, amountPayment, onProcessPayment } = usePayment()
const { setStepCompleted } = useSteps()
const { mutateAsync } = usePaymentStatusMutation()
onMounted(async () => {
  if (hasRedirectResult.value) await checkPaymentStatus()
})
</script>
<template>
  <Card>
    <span>{{ isPartialPayment ? 'Partial payment' : 'Balance Due' }}</span>
    <h1>{{ toMoney(amountPayment) }}</h1>
    <Button @click="onProcessPayment" :loading="isProcessing">Pay Now</Button>
  </Card>
</template>
<!-- ✅ Clean — component only handles UI -->
```
````

<div v-click class="mt-2 grid grid-cols-2 gap-3 text-xs">
  <div class="border border-blue-800 bg-blue-900 bg-opacity-15 rounded p-2">
    <strong class="text-blue-400">Domain:</strong><span class="opacity-70"> usePayment, useSteps, useDeliveryTracking, useDeliverySchedule, usePaymentElement</span>
  </div>
  <div class="border border-blue-800 bg-blue-900 bg-opacity-15 rounded p-2">
    <strong class="text-blue-400">Helpers:</strong><span class="opacity-70"> useGoogleMap, useToast, useEchoChannel, useDownloadFile, useClickOutside, useRouteQuery</span>
  </div>
</div>

<style>
h1 {
  background: linear-gradient(90deg, #42b883, #35d6a0);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.code-sm :deep(pre), .code-sm :deep(code) {
  font-size: 0.65em !important;
  line-height: 1.35 !important;
}
</style>

<!--
Composables extract business logic out of components, making them reusable and independently testable.
Module-level refs allow state sharing between components without a global store.
-->

---
transition: slide-left
class: code-sm
---

# How: Component Pattern

<div class="text-xs opacity-70 mb-2">Two-tier architecture — primitives for UI, compositions for features</div>

````md magic-move {lines: true}
```vue
<!-- Before — atoms/AppButton (Options API + Pug + SCSS) -->
<template lang="pug">
component.btn(:is="tag" :class="[variantClass, loadingClass]")
    .btn__spinner(v-if="loading")
        b-spinner(small)
    .btn__content
        slot
</template>
<script>
export default {
  props: {
    variant: { type: String, default: 'primary' },
    loading: { type: Boolean, default: false },
  },
  computed: {
    variantClass() { return `btn-${this.variant}` },
    loadingClass() { return this.loading ? 'btn-loading' : '' },
  },
}
</script> <!-- + external SCSS -->
<!-- ❌ Pug — non-standard  ❌ No TS  ❌ External SCSS -->
```
```vue
<!-- After (1/2) — primitives/Button (Composition API + TS) -->
<script setup lang="ts">
interface Props {
  color?: 'primary' | 'secondary' | 'danger'
  variant?: 'solid' | 'text' | 'ghost' | 'pill'
  size?: 'sm' | 'md' | 'lg'
  loading?: boolean
}
const props = withDefaults(defineProps<Props>(), {
  color: 'primary', variant: 'solid', size: 'md',
})
const btnClass = computed(() =>
  [baseClasses, sizeClasses[props.size], variantClasses].join(' ')
)
</script>
<template>
  <button :class="btnClass" :disabled="loading">
    <Spinner v-if="loading" :size="size" />
    <slot />
  </button>
</template>
<!-- ✅ TypeScript  ✅ Standard HTML  ✅ Tailwind -->
```
```vue
<!-- After (2/2) — compositions/Payment (primitives + composables) -->
<script setup lang="ts">
const { setStepCompleted } = useSteps()
const { paymentData } = useDeliveryRouteQuery()
const { onProcessPayment } = usePayment()
const { mutateAsync } = usePaymentStatusMutation()
const isVerifying = ref(false)
watch(() => isPaymentConfirmed.value, (confirmed) => {
  if (confirmed) setStepCompleted(paymentData.value?.mode || 0)
}, { immediate: true })
</script>
<template>
  <Card>
    <OrderSummary :data="paymentData" />
    <Button @click="onProcessPayment" :loading="isVerifying">Pay Now</Button>
  </Card>
</template>
<!-- ✅ Primitives + composables  ✅ 26 primitives + 9 compositions -->
```
````

<div v-click class="mt-1 grid grid-cols-2 gap-2 text-xs">
  <div class="border border-purple-800 bg-purple-900 bg-opacity-15 rounded px-2 py-1">
    <strong class="text-purple-400">26 Primitives:</strong><span class="opacity-70"> Button, Input, Modal, Toast, Card, Select, Sheet, Stepper...</span>
  </div>
  <div class="border border-purple-800 bg-purple-900 bg-opacity-15 rounded px-2 py-1">
    <strong class="text-purple-400">9 Compositions:</strong><span class="opacity-70"> Payment, DeliveryTracking, DeliverySchedule, OrderSummary...</span>
  </div>
</div>

<style>
h1 {
  background: linear-gradient(90deg, #42b883, #35d6a0);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.code-sm :deep(pre), .code-sm :deep(code) {
  font-size: 0.65em !important;
  line-height: 1.35 !important;
}
</style>

<!--
Primitives are generic, prop-driven UI components. Compositions combine primitives with business logic via composables.
This two-tier pattern keeps components focused and testable.
-->

---
transition: slide-left
class: code-sm
---

# How: Unit Testing

<div class="text-xs opacity-70 mb-2">From zero test coverage to 101 test files with Vitest</div>

````md magic-move {lines: true}
```json
// Before — package.json (no test tooling)
{
  "scripts": {
    "dev": "nuxt",
    "build": "nuxt build",
    "start": "nuxt start",
    "generate": "nuxt generate"
  },
  "devDependencies": {
    "nuxt": "^2.14.12"
    // ❌ No test runner (Jest, Mocha, Vitest)
    // ❌ No test utilities (Vue Test Utils)
    // ❌ No coverage tool
    // ❌ 0 test files in entire project
  }
}
```
```ts
// After (1/2) — Composable test: usePayment.spec.ts
vi.mock('@/composables/queries/useDeliveryRouteQueries',
  () => ({ useDeliveryRouteQuery: vi.fn() }))

const createMockPayment = (
  overrides: Partial<PaymentResponse['data']> = {},
): PaymentResponse => ({
  mode: 2, data: { order_no: 'TEST-001', ...overrides },
})

describe('usePayment', () => {
  beforeEach(async () => {
    vi.resetModules()
    usePaymentFn = (await import('./usePayment')).usePayment
  })
  it('detects partial payment', () => {
    mockRoute(createMockPayment({ is_partial_payment: 1 }))
    const { isPartialPayment } = usePaymentFn()
    expect(isPartialPayment.value).toBe(true)
  })
})
// ✅ Mock dependencies  ✅ Factory functions  ✅ Isolated state
```
```ts
// After (2/2) — Component test: Button.spec.ts
describe('Button', () => {
  it('renders slot content', () => {
    const wrapper = mount(Button, { slots: { default: 'Click me' } })
    expect(wrapper.text()).toContain('Click me')
    expect(wrapper.element.tagName).toBe('BUTTON')
  })
  it.each([
    { color: 'primary', expected: 'bg-primary' },
    { color: 'secondary', expected: 'bg-secondary' },
    { color: 'danger', expected: 'bg-danger' },
  ])('applies $expected for $color', ({ color, expected }) => {
    const wrapper = mount(Button, { props: { color } })
    expect(wrapper.classes().join(' ')).toContain(expected)
  })
  it('shows spinner when loading', () => {
    const wrapper = mount(Button, { props: { loading: true } })
    expect(wrapper.find('.animate-spin').exists()).toBe(true)
    expect(wrapper.attributes('disabled')).toBeDefined()
  })
})
// ✅ Vue Test Utils  ✅ Parameterized tests  ✅ State assertions
```
````

<div v-click class="mt-1 grid grid-cols-3 gap-2 text-xs">
  <div class="border border-cyan-800 bg-cyan-900 bg-opacity-15 rounded px-2 py-1">
    <strong class="text-cyan-400">Vitest + happy-dom</strong><span class="opacity-70"> — fast, native ESM & TS</span>
  </div>
  <div class="border border-cyan-800 bg-cyan-900 bg-opacity-15 rounded px-2 py-1">
    <strong class="text-cyan-400">101 test files</strong><span class="opacity-70"> — composables, components, utils</span>
  </div>
  <div class="border border-cyan-800 bg-cyan-900 bg-opacity-15 rounded px-2 py-1">
    <strong class="text-cyan-400">@vitest/coverage-v8</strong><span class="opacity-70"> — code coverage reporting</span>
  </div>
</div>

<style>
h1 {
  background: linear-gradient(90deg, #42b883, #35d6a0);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.code-sm :deep(pre), .code-sm :deep(code) {
  font-size: 0.65em !important;
  line-height: 1.35 !important;
}
</style>

<!--
The old project had zero tests — no framework, no test scripts, nothing.
Now we have 101 test files covering composables, components, and utilities.
Vitest + Vue Test Utils + happy-dom gives us fast isolated testing.
-->

---
transition: slide-left
---

# How: PR & Code Coverage Report

<div class="text-xs opacity-70 mb-3">Every pull request is validated by pipeline builds and SonarCloud quality gates</div>

<div class="relative">
  <img src="/assets/images/pr-example.png" class="rounded-lg border border-gray-700 shadow-xl" style="max-height: 340px; width: auto;" />
</div>

<div v-click class="mt-3 grid grid-cols-3 gap-3 text-xs">
  <div class="border border-green-800 bg-green-900 bg-opacity-15 rounded px-3 py-2">
    <carbon-checkmark-filled class="text-green-400 inline mr-1" /><strong class="text-green-400">Quality Gate Passed</strong>
    <div class="opacity-70 mt-1">0 issues · 0 hotspots · 0% duplication</div>
  </div>
  <div class="border border-green-800 bg-green-900 bg-opacity-15 rounded px-3 py-2">
    <carbon-chart-ring class="text-green-400 inline mr-1" /><strong class="text-green-400">100% Coverage</strong>
    <div class="opacity-70 mt-1">All composables, components & utils tested</div>
  </div>
  <div class="border border-blue-800 bg-blue-900 bg-opacity-15 rounded px-3 py-2">
    <carbon-launch class="text-blue-400 inline mr-1" /><strong class="text-blue-400">SonarCloud Dashboard</strong>
    <div class="opacity-70 mt-1"><a href="https://sonarcloud.io/project/overview?id=developer_slymanmedia_appliance-io-customer-portal" target="_blank" class="text-blue-400 underline">View full report →</a></div>
  </div>
</div>

<style>
h1 {
  background: linear-gradient(90deg, #42b883, #35d6a0);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
</style>

<!--
Every PR goes through automated pipeline builds and SonarCloud quality gate checks.
The quality gate enforces zero new issues, zero security hotspots, and code coverage thresholds.
-->

---
transition: slide-left
---

# How: User Flow

<div class="text-xs opacity-70 mb-6">Same journey, elevated experience — zero changes to user flow, enhanced with micro-interactions & pixel-perfect design</div>

<div v-click class="border border-yellow-800 bg-yellow-900 bg-opacity-10 rounded-lg px-5 py-3 text-center mb-8">
  <carbon-arrows-horizontal class="text-yellow-400 inline mr-1 text-lg" /> <strong class="text-yellow-400 text-base">User flow is identical</strong> <span class="opacity-70">— customers see the same steps in the same order, no retraining needed</span>
</div>

<div class="grid grid-cols-2 gap-6">
  <div v-click class="border border-purple-800 bg-purple-900 bg-opacity-10 rounded-lg px-5 py-4">
    <div class="font-semibold text-purple-400 text-base mb-3"><carbon-touch-interaction class="inline mr-1" />Micro-Interactions</div>
    <div class="space-y-2 text-sm opacity-85">
      <div>• Animated price updates on add-on changes</div>
      <div>• Smooth modal open/close transitions</div>
      <div>• Real-time delivery marker animation on map</div>
      <div>• Loading states on async actions</div>
    </div>
  </div>
  <div v-click class="border border-purple-800 bg-purple-900 bg-opacity-10 rounded-lg px-5 py-4">
    <div class="font-semibold text-purple-400 text-base mb-3"><carbon-paint-brush class="inline mr-1" />Pixel-Perfect Design</div>
    <div class="space-y-2 text-sm opacity-85">
      <div>• Consistent spacing via Tailwind design tokens</div>
      <div>• Unified color palette across all steps</div>
      <div>• Responsive layout — mobile to desktop</div>
      <div>• Typography scale with proper hierarchy</div>
      <div>• Accessible contrast ratios (WCAG AA)</div>
    </div>
  </div>
</div>

<style>
h1 {
  background: linear-gradient(90deg, #42b883, #35d6a0);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.slidev-vclick-target {
  transition: none !important;
}
.slidev-vclick-target.slidev-vclick-hidden {
  opacity: 0 !important;
  transform: translateY(12px);
}
.slidev-vclick-target:not(.slidev-vclick-hidden) {
  animation: slideIn 0.4s cubic-bezier(0.25, 1, 0.5, 1) forwards;
}
@keyframes slideIn {
  0% { opacity: 0; transform: translateY(12px); }
  100% { opacity: 1; transform: translateY(0); }
}
</style>

<!--
The user flow remains exactly the same — Review Add-Ons, Payment, Delivery Scheduling, Delivery Tracking.
What changed is the quality of the experience: micro-interactions give instant feedback, and pixel-perfect design ensures visual consistency.
-->

---
transition: slide-left
layout: center
---

# Micro-Interactions: Review Add-Ons

<div class="flex justify-center">
  <video autoplay loop muted playsinline class="rounded-lg border border-gray-700 shadow-xl w-full">
    <source src="/assets/videos/review-addons.mp4" type="video/mp4" />
  </video>
</div>

<div class="text-xs opacity-70 mt-3 text-center">Animated price updates when customers add or remove add-ons</div>

<style>
h1 {
  background: linear-gradient(90deg, #42b883, #35d6a0);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
</style>

<!--
This demo shows the micro-interactions in the Review Add-Ons step — prices animate smoothly when add-ons are toggled.
-->

---
transition: slide-left
layout: center
---

# Micro-Interactions: Delivery Tracking

<div class="flex justify-center">
  <video autoplay loop muted playsinline class="rounded-lg border border-gray-700 shadow-xl w-full">
    <source src="/assets/videos/delivery-tracking.mp4" type="video/mp4" />
  </video>
</div>

<div class="text-xs opacity-70 mt-3 text-center">Real-time delivery marker animation on map with live status updates</div>

<style>
h1 {
  background: linear-gradient(90deg, #42b883, #35d6a0);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
</style>

<!--
This demo shows the delivery tracking micro-interactions — the map marker animates smoothly as the driver's location updates in real-time.
-->

---
transition: slide-left
---

# When: Go-Live Timeline

<div class="text-xs opacity-70 mb-6">When this change goes live and becomes effective</div>

<div class="flex items-center justify-center gap-6 mb-8">
  <div class="border border-gray-700 bg-gray-800 bg-opacity-50 rounded-lg px-8 py-5 text-center flex-1 max-w-xs">
    <carbon-checkmark-filled class="text-green-400 text-3xl mb-2" />
    <div class="text-base font-semibold opacity-70">Current Sprint</div>
    <div class="text-xs opacity-50 mt-1">Development & QA</div>
  </div>
  <div class="text-green-400 text-3xl arrow-pulse">→</div>
  <div class="border border-green-500 bg-green-900 bg-opacity-20 rounded-lg px-8 py-5 text-center flex-1 max-w-xs next-sprint-glow">
    <carbon-rocket class="text-green-400 text-3xl mb-2" />
    <div class="text-lg font-bold text-green-400">Next Sprint</div>
    <div class="text-xs opacity-70 mt-1">Production Release</div>
  </div>
</div>


<style>
h1 {
  background: linear-gradient(90deg, #42b883, #35d6a0);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.next-sprint-glow {
  animation: glow 2s ease-in-out infinite;
}
@keyframes glow {
  0%, 100% { box-shadow: 0 0 8px rgba(34, 197, 94, 0.2); }
  50% { box-shadow: 0 0 20px rgba(34, 197, 94, 0.5); }
}
.arrow-pulse {
  animation: arrowPulse 1.5s ease-in-out infinite;
}
@keyframes arrowPulse {
  0%, 100% { opacity: 0.4; transform: translateX(0); }
  50% { opacity: 1; transform: translateX(6px); }
}
.slidev-vclick-target {
  transition: none !important;
}
.slidev-vclick-target.slidev-vclick-hidden {
  opacity: 0 !important;
  transform: translateY(12px);
}
.slidev-vclick-target:not(.slidev-vclick-hidden) {
  animation: slideIn 0.4s cubic-bezier(0.25, 1, 0.5, 1) forwards;
}
@keyframes slideIn {
  0% { opacity: 0; transform: translateY(12px); }
  100% { opacity: 1; transform: translateY(0); }
}
</style>

<!--
The migration is effectively complete. All development, testing, and code review are done.
Final QA validation is in progress, and the production release is planned for next sprint.
-->

---
transition: slide-left
---

# Customer Portal Storybook

<div class="text-xs opacity-70 mb-4">Living documentation for every UI component in the portal</div>

<div class="grid grid-cols-2 gap-6 items-center">
  <div>
    <img src="/assets/images/storybook-placeholder.png" class="rounded-lg border border-gray-700 shadow-xl w-full" style="max-height: 360px; object-fit: cover; object-position: top;" />
    <div class="mt-2 text-xs text-center">
      <a href="https://customer-docs.appliance.io/" target="_blank" class="text-blue-400 underline">customer-docs.appliance.io →</a>
    </div>
  </div>
  <div class="space-y-4">
    <div class="border border-purple-800 bg-purple-900 bg-opacity-10 rounded-lg px-4 py-3">
      <carbon-view class="text-purple-400 inline mr-1" /><strong class="text-purple-400">Interactive Previews</strong>
      <div class="text-xs opacity-70 mt-1">Browse and interact with every primitive and composition in isolation</div>
    </div>
    <div class="border border-cyan-800 bg-cyan-900 bg-opacity-10 rounded-lg px-4 py-3">
      <carbon-document class="text-cyan-400 inline mr-1" /><strong class="text-cyan-400">Props & Variants</strong>
      <div class="text-xs opacity-70 mt-1">Explore all available props, states, and visual variants per component</div>
    </div>
    <div class="border border-green-800 bg-green-900 bg-opacity-10 rounded-lg px-4 py-3">
      <carbon-group class="text-green-400 inline mr-1" /><strong class="text-green-400">Design–Dev Alignment</strong>
      <div class="text-xs opacity-70 mt-1">Single source of truth for QA, designers, and developers</div>
    </div>
  </div>
</div>

<style>
h1 {
  background: linear-gradient(90deg, #42b883, #35d6a0);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
</style>

<!--
The Storybook serves as living documentation — every component can be viewed, tested, and validated in isolation.
This bridges the gap between design and development and gives QA a visual reference for every UI state.
-->

---
layout: cover
transition: fade
---

<div class="flex flex-col items-center justify-center text-center">
  <div class="text-6xl mb-6 closing-icon"><carbon-favorite-filled class="text-red-400" /></div>
  <h1 class="!text-4xl !leading-tight mb-4">Happy Developers,<br/>Better Products</h1>
  <div class="text-lg opacity-70 max-w-lg">When developers love their tools, users love the product. Modern stack, clean architecture, and developer joy — that's how great software gets shipped.</div>
  <div class="mt-8 text-2xl font-bold opacity-90">Thank You!</div>
  <div class="mt-2 text-sm opacity-50">Customer Portal Migration — Vue 2 → Vue 3</div>
</div>

<style>
.slidev-layout {
  background: linear-gradient(135deg, #1a1a2e 0%, #16213e 40%, #0f3460 100%) !important;
  overflow: hidden;
}
.slidev-layout::before {
  content: '';
  position: absolute;
  top: -80px;
  right: -80px;
  width: 480px;
  height: 480px;
  background: radial-gradient(circle, rgba(66, 184, 131, 0.15) 0%, transparent 70%);
  pointer-events: none;
  z-index: 0;
}
.slidev-layout::after {
  content: '';
  position: absolute;
  bottom: -120px;
  left: -100px;
  width: 400px;
  height: 400px;
  background: radial-gradient(circle, rgba(66, 184, 131, 0.1) 0%, transparent 70%);
  pointer-events: none;
  z-index: 0;
}
h1 {
  background: linear-gradient(135deg, #42b883, #35d6a0, #42b883);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.closing-icon {
  animation: pulse 2s ease-in-out infinite;
}
@keyframes pulse {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.15); }
}
</style>

<!--
Closing statement: investing in developer experience directly translates to better product quality and faster delivery.
-->
