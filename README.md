import React, { useEffect, useState } from "react";

// Minecraft Server Website Starter (single-file React component)
// - Tailwind CSS assumed present
// - Replace placeholder data / endpoints with your backend or CMS
// - Export default App to drop into a React app (Next.js, Vite, CRA)

export default function MinecraftServerWebsiteStarter() {
  return (
    <div className="min-h-screen bg-gradient-to-b from-gray-900 via-gray-800 to-black text-gray-100 font-sans">
      <Header />
      <main className="max-w-6xl mx-auto p-6">
        <Hero />
        <div className="grid gap-8 lg:grid-cols-3 mt-8">
          <div className="lg:col-span-2 space-y-6">
            <News />
            <Events />
          </div>

          <aside className="space-y-6">
            <ServerStatus />
            <DiscordCard />
            <DonateCard />
            <StaffCard />
          </aside>
        </div>

        <Footer />
      </main>
    </div>
  );
}

function Header() {
  return (
    <header className="flex items-center justify-between py-4">
      <div className="flex items-center gap-4">
        <div className="w-12 h-12 bg-gradient-to-br from-green-400 to-emerald-600 rounded-md flex items-center justify-center text-black font-bold">MC</div>
        <div>
          <h1 className="text-xl font-semibold">YourServerName</h1>
          <p className="text-xs text-gray-300">Vanilla / Survival / Creative</p>
        </div>
      </div>

      <nav className="flex items-center gap-4">
        <a className="text-sm hover:underline" href="#news">Tin tức</a>
        <a className="text-sm hover:underline" href="#events">Sự kiện</a>
        <a className="text-sm hover:underline" href="#discord">Discord</a>
        <a className="inline-flex items-center gap-2 bg-emerald-500 text-black px-3 py-2 rounded-md text-sm" href="/download">Kết nối</a>
      </nav>
    </header>
  );
}

function Hero() {
  return (
    <section className="bg-[url('https://images.unsplash.com/photo-1549887534-38f5b6b8b7a3?q=80&w=1600&auto=format&fit=crop&s=placeholder')] bg-cover bg-center rounded-2xl p-8 shadow-2xl">
      <div className="backdrop-brightness-75 p-6 rounded-lg">
        <h2 className="text-3xl font-extrabold">Chào mừng đến với YourServerName</h2>
        <p className="mt-2 text-gray-200 max-w-2xl">Tham gia cộng đồng, tham dự sự kiện hàng tuần, kiếm phần thưởng, và xây dựng thế giới mơ ước của bạn.</p>

        <div className="mt-6 flex gap-3">
          <a className="px-5 py-3 rounded-lg bg-emerald-500 text-black font-semibold" href="/connect">Kết nối ngay</a>
          <a className="px-5 py-3 rounded-lg border border-gray-600 text-sm" href="#events">Xem sự kiện</a>
        </div>

        <div className="mt-6 text-sm text-gray-300">IP: <strong>play.yourserver.com</strong> • Mode: Survival</div>
      </div>
    </section>
  );
}

// ---------- NEWS ----------
function News() {
  // In production, fetch from /api/news
  const [news, setNews] = useState(sampleNews);

  // Example of how to fetch live news (uncomment & adapt):
  // useEffect(() => {
  //   fetch('/api/news')
  //     .then(r => r.json())
  //     .then(setNews)
  //     .catch(() => setNews(sampleNews));
  // }, []);

  return (
    <section id="news" className="bg-gray-900/40 p-5 rounded-lg">
      <div className="flex items-center justify-between">
        <h3 className="text-2xl font-bold">Tin tức</h3>
        <a className="text-sm text-gray-300 hover:underline" href="/news">Tất cả</a>
      </div>

      <ul className="mt-4 space-y-4">
        {news.map((n) => (
          <li key={n.id} className="p-4 bg-gray-800/40 rounded-md hover:scale-[1.01] transition-transform">
            <a href={`/news/${n.id}`} className="flex items-start gap-4">
              <img src={n.image} alt="thumbnail" className="w-28 h-16 object-cover rounded-md flex-shrink-0" />
              <div>
                <h4 className="font-semibold">{n.title}</h4>
                <p className="text-xs text-gray-300">{n.date} • {n.excerpt}</p>
              </div>
            </a>
          </li>
        ))}
      </ul>
    </section>
  );
}

const sampleNews = [
  { id: '1', title: 'Update 1.20: Thêm tính năng mới', date: '2025-12-01', excerpt: 'Bản cập nhật lớn với biome mới và items...', image: 'https://images.unsplash.com/photo-1549887534-38f5b6b8b7a3?q=80&w=800&auto=format&fit=crop&s=placeholder' },
  { id: '2', title: 'Event: Cuộc đua xây dựng', date: '2025-11-20', excerpt: 'Cuộc thi xây dựng với phần thưởng hấp dẫn.', image: 'https://images.unsplash.com/photo-1526318472351-c75fcf0704d7?q=80&w=800&auto=format&fit=crop&s=placeholder' },
];

// ---------- EVENTS ----------
function Events() {
  // Placeholder events; replace by /api/events
  const [events, setEvents] = useState(sampleEvents);

  // Example fetch similar to News.
  return (
    <section id="events" className="bg-gray-900/40 p-5 rounded-lg">
      <div className="flex items-center justify-between">
        <h3 className="text-2xl font-bold">Sự kiện sắp tới</h3>
        <a className="text-sm text-gray-300 hover:underline" href="/events">Tất cả</a>
      </div>

      <div className="mt-4 space-y-3">
        {events.map((e) => (
          <div key={e.id} className="p-4 bg-gray-800/30 rounded-md flex items-center justify-between">
            <div>
              <div className="text-sm text-gray-300">{e.date} • {e.time}</div>
              <div className="font-semibold">{e.title}</div>
              <div className="text-xs text-gray-300">{e.description}</div>
            </div>
            <a className="px-3 py-2 text-sm rounded-md border border-gray-700" href={`/events/${e.id}`}>Chi tiết</a>
          </div>
        ))}
      </div>
    </section>
  );
}

const sampleEvents = [
  { id: 'e1', title: 'Build Battle (Team)', date: '2025-12-10', time: '19:00', description: 'Thi đấu theo đội, chủ đề: Lâu đài' },
  { id: 'e2', title: 'PvP Tournament', date: '2025-12-17', time: '20:00', description: 'Loại trực tiếp, giải thưởng bằng items in-game' },
];

// ---------- SERVER STATUS ----------
function ServerStatus() {
  const [status, setStatus] = useState({ online: false, players: 0, max: 0 });

  useEffect(() => {
    // Replace with your server status API or ping library
    // Example: /api/status -> { online: true, players: 5, max: 100 }
    // For demo we set a timeout to simulate fetching
    const t = setTimeout(() => {
      setStatus({ online: true, players: 12, max: 120 });
    }, 400);

    return () => clearTimeout(t);
  }, []);

  return (
    <div className="p-4 bg-gray-900/40 rounded-lg">
      <h4 className="font-semibold">Trạng thái server</h4>
      <div className="mt-3 flex items-center justify-between">
        <div>
          <div className={`inline-block px-3 py-1 rounded-full text-sm ${status.online ? 'bg-emerald-500 text-black' : 'bg-red-600'}`}>
            {status.online ? 'Online' : 'Offline'}
          </div>

          <div className="text-xs text-gray-300 mt-2">Người chơi: {status.players}/{status.max}</div>
        </div>
        <div className="text-right text-xs text-gray-400">IP: play.yourserver.com<br />Port: 25565</div>
      </div>
    </div>
  );
}

function DiscordCard() {
  return (
    <div id="discord" className="p-4 bg-gray-900/40 rounded-lg">
      <h4 className="font-semibold">Discord</h4>
      <p className="text-xs text-gray-300 mt-2">Tham gia cộng đồng trên Discord để nhận thông báo nhanh.</p>

      {/* Replace the iframe src with your server's Discord widget URL (requires server ID) */}
      <div className="mt-3">
        <div className="w-full h-36 bg-gradient-to-b from-gray-800 to-gray-900 rounded-md flex items-center justify-center text-gray-400 text-sm">Discord widget preview</div>
      </div>

      <a className="mt-3 inline-block text-sm underline text-gray-300" href="https://discord.gg/your-invite">Tham gia Discord</a>
    </div>
  );
}

function DonateCard() {
  return (
    <div className="p-4 bg-gray-900/40 rounded-lg">
      <h4 className="font-semibold">Ủng hộ server</h4>
      <p className="text-xs text-gray-300 mt-2">Hỗ trợ chi phí vận hành để giữ server hoạt động ổn định, nhận rank & perks.</p>
      <div className="mt-4 flex gap-2">
        <a className="px-3 py-2 rounded-md bg-amber-400 text-black text-sm" href="/donate">Donate</a>
        <a className="px-3 py-2 rounded-md border border-gray-700 text-sm" href="/store">Cửa hàng</a>
      </div>
    </div>
  );
}

function StaffCard() {
  return (
    <div className="p-4 bg-gray-900/40 rounded-lg">
      <h4 className="font-semibold">Ban quản trị</h4>
      <ul className="mt-3 text-sm text-gray-300 space-y-2">
        <li>Haooo – Owner</li>
        <li>Player1 – Admin</li>
        <li>Builder2 – Builder</li>
      </ul>
    </div>
  );
}

function Footer() {
  return (
    <footer className="mt-10 text-center text-xs text-gray-400 p-6">
      <div>© {new Date().getFullYear()} YourServerName — Đã đăng ký bản quyền</div>
      <div className="mt-2">Made with ❤️ for your community • <a className="underline" href="/staff">Liên hệ</a></div>
    </footer>
  );
}

// ----------------- NOTES -----------------
// - Replace sample data with your CMS or REST endpoints.
// - Consider: Next.js for SSR, Supabase/PlanetScale for DB, Strapi/Headless CMS for editors.
// - For events/news CMS: use a simple admin page to create/edit posts (or use Netlify/Contentful/Strapi).
// - For server status: use a Minecraft server ping library (e.g. 'minecraft-server-util') on the backend and expose /api/status.
// - For authentication (staff/admin): use OAuth (Discord) + role checks.

// Optional: Provide example API responses used by this component
export const exampleApi = {
  '/api/news': sampleNews,
  '/api/events': sampleEvents,
  '/api/status': { online: true, players: 12, max: 120 },
};
