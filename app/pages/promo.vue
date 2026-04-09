<script setup>
const ONE_LOST_RULES = [
  { min: 20, max: 44, percent: 1.0 },
  { min: 45, max: 89, percent: 3.0 },
  { min: 90, max: 144, percent: 6.0 },
  { min: 145, max: 199, percent: 9.0 },
  { min: 200, max: 499, percent: 12.0 },
  { min: 500, max: 999, percent: 18.0 },
  { min: 1000, max: 1799, percent: 31.5 },
  { min: 1800, max: Infinity, percent: 100.0 },
];

const TWO_LOST_RULES = [
  { min: 20, max: 44, percent: 1.0 },
  { min: 45, max: 59, percent: 2.5 },
  { min: 60, max: 89, percent: 3.5 },
  { min: 90, max: 449, percent: 6.0 },
  { min: 450, max: 999, percent: 12.0 },
  { min: 1000, max: 1799, percent: 21.0 },
  { min: 1800, max: Infinity, percent: 50.0 },
];
</script>

<template>
  <div
    class="min-h-screen bg-[#DBDBDB] text-white font-sans selection:bg-[#DB7C2E]"
  >
    <header class="relative py-20 px-6 text-center overflow-hidden">
      <div
        class="absolute top-0 left-1/2 -translate-x-1/2 w-full h-64 bg-[#8E213A] opacity-20 blur-[120px] rounded-full"
      ></div>

      <div class="relative z-10">
        <h1
          class="text-2xl md:text-5xl md:text-7xl font-black tracking-tighter mb-4 uppercase italic text-black"
        >
          Lost by a <span class="text-[#DB7C2E]">One or Two matches?</span>
          <br />
          <span class="tracking-wider"
            >ቲኬትዎ በ1 ወይም 2 ጨዋታዎች የወደቀ ነው? አይዞዎት አለንልዎት።</span
          >
        </h1>
        <p
          class="text-lg md:text-xl text-gray-900 max-w-2xl mx-auto font-light"
        >
          Don't let one or two bad results ruin your parlay. We’ve built a
          massive
          <span class="text-black font-bold">Cashback Safety Net</span> just for
          you.
        </p>
      </div>
    </header>

    <main class="max-w-6xl mx-auto px-6 pb-12">
      <div class="grid lg:grid-cols-2 gap-10">
        <section
          class="group bg-[#1F1F1F] rounded-2xl overflow-hidden border border-[#8E213A]/30 shadow-2xl transition-all hover:border-[#8E213A]"
        >
          <div class="bg-[#49215D] p-6 text-center space-y-1">
            <h2
              class="text-xl md:text-3xl font-black tracking-widest uppercase italic"
            >
              1 Leg Missed <br />
              በ1 የወደቀ ቲኬት
            </h2>
            <p class="text-sm opacity-80 uppercase tracking-tighter">
              Maximum Return <br />
              ከፍተኛ ተመላሽ
            </p>
          </div>

          <div class="p-6 space-y-2">
            <div
              v-for="rule in ONE_LOST_RULES"
              :key="rule.min"
              class="flex justify-between items-center p-4 bg-[#DBDBDB] rounded-lg border border-transparent hover:border-[#DB7C2E]/50 transition-all"
            >
              <div>
                <span class="text-xs block uppercase font-bold text-black"
                  >Odds Range</span
                >
                <span class="text-lg font-mono text-gray-800">
                  {{ rule.min
                  }}{{ rule.max === Infinity ? "+" : " - " + rule.max }}
                </span>
              </div>
              <div class="text-right">
                <span
                  class="text-xs text-[#000] block uppercase font-bold text-right"
                  >Refund | ተመላሽ</span
                >
                <span class="text-2xl font-black text-[#49215D]"
                  >{{ rule.percent * 100 }}%</span
                >
              </div>
            </div>
          </div>
        </section>

        <section
          class="group bg-[#1F1F1F] rounded-2xl overflow-hidden border border-gray-800 shadow-2xl transition-all hover:border-[#DB7C2E]"
        >
          <div class="bg-[#49215D] p-6 text-center space-y-1">
            <h2
              class="text-xl md:text-3xl font-black tracking-widest uppercase italic"
            >
              2 Leg Missed <br />
              በ2 የወደቀ ቲኬት
            </h2>
            <p class="text-sm opacity-80 uppercase tracking-tighter">
              Maximum Return <br />
              ከፍተኛ ተመላሽ
            </p>
          </div>

          <div class="p-6 space-y-2">
            <div
              v-for="rule in TWO_LOST_RULES"
              :key="rule.min"
              class="flex justify-between items-center p-4 bg-[#DBDBDB] rounded-lg border border-transparent hover:border-[#DB7C2E]/50 transition-all"
            >
              <div>
                <span class="text-xs text-gray-900 block uppercase font-bold"
                  >Odds Range | ቀሪ ኦድ</span
                >
                <span class="text-lg font-mono text-gray-800">
                  {{ rule.min
                  }}{{ rule.max === Infinity ? "+" : " - " + rule.max }}
                </span>
              </div>
              <div class="text-right">
                <span
                  class="text-xs text-[#49215D] block uppercase font-bold text-right"
                  >Refund | ተመላሽ</span
                >
                <span class="text-2xl font-black text-[#49215D]"
                  >{{ rule.percent * 100 }}%</span
                >
              </div>
            </div>
          </div>
        </section>
      </div>

      <footer
        class="mt-16 text-center p-8 bg-[#49215D] rounded-xl border-t-4 border-[#a021e0]"
      >
        <h3 class="text-[#fff] font-bold uppercase tracking-widest mb-4">
          ህጎና ደንቦች
        </h3>
        <p class="text-sm text-gray-200 max-w-3xl mx-auto leading-relaxed">
          በተመላሽ ገንዝብ ስሌት ላይ የሚያገለግሉት ያልውድቁ ጨዋታዎች ኦዶች ብቻ ናቸው። ዝቅተኛ መነሻ ኦድ ከ20 በላይ
          ነው።
        </p>
      </footer>
    </main>
  </div>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@300;400;700;900&display=swap");

.font-sans {
  font-family: "Inter", sans-serif;
}
</style>
