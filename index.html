import { createFileRoute } from "@tanstack/react-router";
import { useCallback, useMemo, useRef, useState } from "react";
import { cuteNames, motivationalLines } from "@/lib/bubble-data";

export const Route = createFileRoute("/")({
  head: () => ({
    meta: [
      { title: "For My Shikhar 💕 | Pop Some Love" },
      {
        name: "description",
        content:
          "A cute little world of heart bubbles filled with sweet names and love for Shikhar. Pop them for a smile.",
      },
      { property: "og:title", content: "For My Shikhar 💕" },
      {
        property: "og:description",
        content: "Pop the pink heart bubbles for cute names and sweet motivation.",
      },
      { property: "og:type", content: "website" },
    ],
  }),
  component: BubblePage,
});

const BATCH_SIZE = 13;

type Bubble = {
  id: number;
  message: string;
  isName: boolean;
  left: number;
  top: number;
  size: number;
  floatDur: number;
  delay: number;
  hue: number;
};

// Fisher-Yates shuffle for a fresh, non-repeating order.
function shuffle<T>(arr: T[]): T[] {
  const a = [...arr];
  for (let i = a.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [a[i], a[j]] = [a[j], a[i]];
  }
  return a;
}

function BubblePage() {
  // All 200 messages, shuffled once. We consume them in order so nothing
  // repeats until every bubble has been seen.
  const deck = useRef<{ message: string; isName: boolean }[]>(
    shuffle([
      ...cuteNames.map((message) => ({ message, isName: true })),
      ...motivationalLines.map((message) => ({ message, isName: false })),
    ]),
  );
  const cursor = useRef(0);
  const bubbleId = useRef(0);

  const [bubbles, setBubbles] = useState<Bubble[]>([]);
  const [popped, setPopped] = useState<number[]>([]);
  const [popping, setPopping] = useState<Record<number, boolean>>({});
  const [seen, setSeen] = useState(0);

  const buildBatch = useCallback((): Bubble[] => {
    const batch: Bubble[] = [];
    for (let i = 0; i < BATCH_SIZE; i++) {
      if (cursor.current >= deck.current.length) {
        // All 200 seen — reshuffle and allow repeats from here on.
        deck.current = shuffle(deck.current);
        cursor.current = 0;
      }
      const item = deck.current[cursor.current++];
      batch.push({
        id: bubbleId.current++,
        message: item.message,
        isName: item.isName,
        left: 6 + Math.random() * 82,
        top: 8 + Math.random() * 74,
        size: 92 + Math.random() * 58,
        floatDur: 3.5 + Math.random() * 3,
        delay: Math.random() * 0.5,
        hue: Math.random() * 24 - 12,
      });
    }
    return batch;
  }, []);

  const play = useCallback(() => {
    setPopped([]);
    setPopping({});
    const batch = buildBatch();
    setBubbles(batch);
    setSeen((s) => s + batch.length);
  }, [buildBatch]);

  const popBubble = useCallback((b: Bubble) => {
    setPopping((p) => ({ ...p, [b.id]: true }));
    setPopped((prev) => [...prev, b.id]);
  }, []);

  const started = bubbles.length > 0;
  const allPopped = started && popped.length === bubbles.length;
  const totalUnique = cuteNames.length + motivationalLines.length;

  const sparkles = useMemo(
    () =>
      Array.from({ length: 22 }).map((_, i) => ({
        id: i,
        left: Math.random() * 100,
        top: Math.random() * 100,
        dur: 2 + Math.random() * 3,
        delay: Math.random() * 4,
        size: 6 + Math.random() * 10,
      })),
    [],
  );

  return (
    <div className="dreamy-bg relative min-h-screen overflow-hidden px-4 py-10">
      {/* floating sparkles */}
      {sparkles.map((s) => (
        <span
          key={s.id}
          className="animate-twinkle pointer-events-none absolute select-none"
          style={{
            left: `${s.left}%`,
            top: `${s.top}%`,
            fontSize: `${s.size}px`,
            animationDuration: `${s.dur}s`,
            animationDelay: `${s.delay}s`,
          }}
        >
          ✨
        </span>
      ))}

      <header className="relative z-10 mx-auto max-w-2xl text-center">
        <p className="animate-wobble inline-block text-4xl">💖</p>
        <h1
          className="mt-2 bg-gradient-to-r from-[oklch(0.7_0.15_5)] via-[oklch(0.75_0.15_350)] to-[oklch(0.72_0.14_20)] bg-clip-text text-4xl font-extrabold tracking-tight text-transparent sm:text-5xl"
          style={{ fontFamily: "system-ui, 'Segoe UI', sans-serif" }}
        >
          for my shikhar
        </h1>
        <p className="mt-3 text-sm font-medium text-[oklch(0.55_0.08_5)] sm:text-base">
          pop the little pink hearts for a cute name or a sweet reminder 🫧
        </p>
        <p className="mt-1 text-xs text-[oklch(0.6_0.05_5)]">
          you popped {popped.length}/{started ? bubbles.length : 0} · {Math.min(seen, totalUnique)} of{" "}
          {totalUnique} loves discovered
        </p>
      </header>

      {/* play area */}
      <div className="relative z-0 mx-auto mt-6 h-[62vh] max-w-4xl">
        {!started && (
          <div className="flex h-full flex-col items-center justify-center text-center">
            <p className="mb-6 max-w-md text-base font-medium text-[oklch(0.5_0.08_5)]">
              hi baby 💌 tap the heart below and start popping bubbles. each one has
              something just for you.
            </p>
            <PlayButton onClick={play} label="start popping 🫧" />
          </div>
        )}

        {bubbles.map((b) => {
          const isPopping = popping[b.id];
          return (
            <button
              key={b.id}
              onClick={() => !isPopping && popBubble(b)}
              className={`group absolute flex items-center justify-center focus:outline-none ${
                isPopping ? "animate-pop pointer-events-none" : "animate-bubble-in"
              }`}
              style={{
                left: `${b.left}%`,
                top: `${b.top}%`,
                width: `${b.size}px`,
                height: `${b.size}px`,
                animationDelay: `${b.delay}s`,
              }}
              aria-label="pop heart bubble"
            >
              <span
                className="animate-float relative flex h-full w-full items-center justify-center"
                style={{ animationDuration: `${b.floatDur}s` }}
              >
                <svg
                  viewBox="0 0 100 100"
                  className="h-full w-full drop-shadow-[0_8px_18px_oklch(0.7_0.15_5/0.45)] transition-transform duration-300 group-hover:scale-110 group-active:scale-95"
                >
                  <defs>
                    <radialGradient id={`hg-${b.id}`} cx="35%" cy="28%" r="75%">
                      <stop offset="0%" stopColor={`oklch(0.98 0.03 ${350 + b.hue})`} />
                      <stop offset="55%" stopColor={`oklch(0.86 0.1 ${5 + b.hue})`} />
                      <stop offset="100%" stopColor={`oklch(0.78 0.14 ${5 + b.hue})`} />
                    </radialGradient>
                  </defs>
                  <path
                    d="M50 86 C22 66 8 48 8 30 C8 17 18 8 30 8 C39 8 46 14 50 22 C54 14 61 8 70 8 C82 8 92 17 92 30 C92 48 78 66 50 86 Z"
                    fill={`url(#hg-${b.id})`}
                  />
                  <ellipse cx="34" cy="30" rx="7" ry="5" fill="oklch(1 0 0 / 0.65)" />
                </svg>
              </span>
            </button>
          );
        })}

        {/* popped messages float where bubbles were */}
        {bubbles
          .filter((b) => popped.includes(b.id))
          .map((b) => (
            <div
              key={`msg-${b.id}`}
              className="animate-bubble-in pointer-events-none absolute -translate-x-1/2 -translate-y-1/2 text-center"
              style={{ left: `${b.left + b.size / 40}%`, top: `${b.top + b.size / 40}%` }}
            >
              <span
                className={`whitespace-nowrap rounded-full px-3 py-1 text-xs font-bold shadow-md backdrop-blur ${
                  b.isName
                    ? "bg-[oklch(0.95_0.06_350/0.9)] text-[oklch(0.55_0.15_5)]"
                    : "bg-[oklch(0.96_0.04_320/0.9)] text-[oklch(0.5_0.1_320)]"
                }`}
              >
                {b.isName ? "💕 " : "🌸 "}
                {b.message}
              </span>
            </div>
          ))}
      </div>

      {/* controls */}
      {started && (
        <div className="relative z-10 mx-auto mt-2 flex max-w-md flex-col items-center gap-3 text-center">
          {allPopped && (
            <p className="animate-bubble-in text-sm font-semibold text-[oklch(0.55_0.12_5)]">
              you popped them all, my love 🥰 here comes more!
            </p>
          )}
          <PlayButton onClick={play} label="play again 🔁" />
        </div>
      )}

      <footer className="relative z-10 mt-8 text-center text-xs text-[oklch(0.6_0.05_5)]">
        made with 💗 just for you, shikhar
      </footer>
    </div>
  );
}

function PlayButton({ onClick, label }: { onClick: () => void; label: string }) {
  return (
    <button
      onClick={onClick}
      className="rounded-full bg-gradient-to-r from-[oklch(0.78_0.14_5)] to-[oklch(0.75_0.14_340)] px-8 py-3 text-base font-bold text-white shadow-[0_10px_25px_-8px_oklch(0.7_0.15_5/0.8)] transition-all duration-300 hover:-translate-y-0.5 hover:scale-105 hover:shadow-[0_14px_30px_-8px_oklch(0.7_0.15_5/0.9)] active:scale-95"
    >
      {label}
    </button>
  );
}
