
Action: $ cd /app/frontend && yarn add @phosphor-icons/react framer-motion 2>&1 | tail -5
Observation: info All dependencies
├─ @phosphor-icons/react@2.1.10
├─ framer-motion@12.39.0
└─ motion-dom@12.39.0
Done in 49.86s.
Exit code: 0



Action: file_editor create /app/frontend/tailwind.config.js --file-text "/** @type {import('tailwindcss').Config} */
module.exports = {
    darkMode: [\"class\"],
    content: [
        \"./src/**/*.{js,jsx,ts,tsx}\",
        \"./public/index.html\"
    ],
    theme: {
        extend: {
            fontFamily: {
                heading: ['\"Cabinet Grotesk\"', 'sans-serif'],
                body: ['Manrope', 'sans-serif'],
            },
            borderRadius: {
                lg: 'var(--radius)',
                md: 'calc(var(--radius) - 2px)',
                sm: 'calc(var(--radius) - 4px)'
            },
            colors: {
                background: 'hsl(var(--background))',
                foreground: 'hsl(var(--foreground))',
                card: {
                    DEFAULT: 'hsl(var(--card))',
                    foreground: 'hsl(var(--card-foreground))'
                },
                popover: {
                    DEFAULT: 'hsl(var(--popover))',
                    foreground: 'hsl(var(--popover-foreground))'
                },
                primary: {
                    DEFAULT: 'hsl(var(--primary))',
                    foreground: 'hsl(var(--primary-foreground))'
                },
                secondary: {
                    DEFAULT: 'hsl(var(--secondary))',
                    foreground: 'hsl(var(--secondary-foreground))'
                },
                muted: {
                    DEFAULT: 'hsl(var(--muted))',
                    foreground: 'hsl(var(--muted-foreground))'
                },
                accent: {
                    DEFAULT: 'hsl(var(--accent))',
                    foreground: 'hsl(var(--accent-foreground))'
                },
                destructive: {
                    DEFAULT: 'hsl(var(--destructive))',
                    foreground: 'hsl(var(--destructive-foreground))'
                },
                border: 'hsl(var(--border))',
                input: 'hsl(var(--input))',
                ring: 'hsl(var(--ring))',
                clay: {
                    bg: '#FBF9F6',
                    surface: '#FFFFFF',
                    forest: '#2B5C4B',
                    forestDark: '#1E4336',
                    terracotta: '#E27D60',
                    sand: '#F2EBE1',
                    ink: '#1A1A1A',
                    mute: '#5C5C5C',
                    line: '#E5DFD3',
                },
            },
            keyframes: {
                'accordion-down': { from: { height: '0' }, to: { height: 'var(--radix-accordion-content-height)' } },
                'accordion-up': { from: { height: 'var(--radix-accordion-content-height)' }, to: { height: '0' } },
                'marquee': {
                    '0%': { transform: 'translateX(0)' },
                    '100%': { transform: 'translateX(-50%)' },
                },
            },
            animation: {
                'accordion-down': 'accordion-down 0.2s ease-out',
                'accordion-up': 'accordion-up 0.2s ease-out',
                'marquee': 'marquee 40s linear infinite',
            }
        }
    },
    plugins: [require(\"tailwindcss-animate\")],
};
"
Observation: Overwrite successful: /app/frontend/tailwind.config.js



Action: file_editor create /app/frontend/src/index.css --file-text "@import url('https://api.fontshare.com/v2/css?f[]=cabinet-grotesk@400,500,700,800&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Manrope:wght@300;400;500;600;700&display=swap');

@tailwind base;
@tailwind components;
@tailwind utilities;

html {
    scroll-behavior: smooth;
}

body {
    margin: 0;
    font-family: 'Manrope', sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    background: #FBF9F6;
    color: #1A1A1A;
}

::selection {
    background: #2B5C4B;
    color: #FBF9F6;
}

@layer base {
    :root {
        --background: 38 33% 97%;
        --foreground: 0 0% 10%;
        --card: 0 0% 100%;
        --card-foreground: 0 0% 10%;
        --popover: 0 0% 100%;
        --popover-foreground: 0 0% 10%;
        --primary: 156 37% 26%;
        --primary-foreground: 38 33% 97%;
        --secondary: 38 33% 92%;
        --secondary-foreground: 156 37% 26%;
        --muted: 38 33% 92%;
        --muted-foreground: 0 0% 36%;
        --accent: 38 33% 92%;
        --accent-foreground: 156 37% 26%;
        --destructive: 0 84.2% 60.2%;
        --destructive-foreground: 0 0% 98%;
        --border: 36 23% 84%;
        --input: 36 23% 84%;
        --ring: 156 37% 26%;
        --radius: 0.75rem;
    }
}

@layer base {
    * {
        @apply border-border;
    }
    body {
        @apply bg-background text-foreground font-body;
    }
    h1, h2, h3, h4, h5, h6 {
        font-family: 'Cabinet Grotesk', sans-serif;
        letter-spacing: -0.01em;
    }
}

.font-heading {
    font-family: 'Cabinet Grotesk', sans-serif;
    letter-spacing: -0.015em;
}

.font-body {
    font-family: 'Manrope', sans-serif;
}

.eyebrow {
    font-family: 'Manrope', sans-serif;
    font-size: 0.7rem;
    letter-spacing: 0.22em;
    text-transform: uppercase;
    font-weight: 600;
    color: #2B5C4B;
}

/* Grain texture overlay */
.grain::before {
    content: '';
    position: absolute;
    inset: 0;
    pointer-events: none;
    opacity: 0.4;
    background-image: url(\"data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='2'/%3E%3CfeColorMatrix values='0 0 0 0 0  0 0 0 0 0  0 0 0 0 0  0 0 0 0.08 0'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E\");
    mix-blend-mode: multiply;
}

.scroll-hide::-webkit-scrollbar { display: none; }
.scroll-hide { -ms-overflow-style: none; scrollbar-width: none; }

@layer base {
    [data-debug-wrapper=\"true\"] {
        display: contents !important;
    }
    [data-debug-wrapper=\"true\"] > * {
        margin-left: inherit;
        margin-right: inherit;
        margin-top: inherit;
        margin-bottom: inherit;
        padding-left: inherit;
        padding-right: inherit;
        padding-top: inherit;
        padding-bottom: inherit;
        column-gap: inherit;
        row-gap: inherit;
        gap: inherit;
    }
}
"
Observation: Overwrite successful: /app/frontend/src/index.css




Action: file_editor create /app/frontend/src/App.css --file-text ".App {
    min-height: 100vh;
}
"
Observation: Overwrite successful: /app/frontend/src/App.css




Now let me build the backend with appointments, and all frontend components in parallel.
Action: file_editor create /app/backend/server.py --file-text "from fastapi import FastAPI, APIRouter, HTTPException
from dotenv import load_dotenv
from starlette.middleware.cors import CORSMiddleware
from motor.motor_asyncio import AsyncIOMotorClient
import os
import logging
from pathlib import Path
from pydantic import BaseModel, Field, ConfigDict, EmailStr
from typing import List, Optional
import uuid
from datetime import datetime, timezone


ROOT_DIR = Path(__file__).parent
load_dotenv(ROOT_DIR / '.env')

# MongoDB connection
mongo_url = os.environ['MONGO_URL']
client = AsyncIOMotorClient(mongo_url)
db = client[os.environ['DB_NAME']]

# Create the main app without a prefix
app = FastAPI(title=\"Apex Diagnostics API\")

# Create a router with the /api prefix
api_router = APIRouter(prefix=\"/api\")


# ========== Models ==========

class AppointmentCreate(BaseModel):
    full_name: str = Field(..., min_length=2, max_length=100)
    phone: str = Field(..., min_length=7, max_length=20)
    email: Optional[EmailStr] = None
    service: str = Field(..., min_length=2, max_length=100)
    preferred_date: Optional[str] = None
    preferred_time: Optional[str] = None
    message: Optional[str] = Field(None, max_length=500)


class Appointment(BaseModel):
    model_config = ConfigDict(extra=\"ignore\")

    id: str = Field(default_factory=lambda: str(uuid.uuid4()))
    full_name: str
    phone: str
    email: Optional[str] = None
    service: str
    preferred_date: Optional[str] = None
    preferred_time: Optional[str] = None
    message: Optional[str] = None
    status: str = \"pending\"
    created_at: datetime = Field(default_factory=lambda: datetime.now(timezone.utc))


# ========== Routes ==========

@api_router.get(\"/\")
async def root():
    return {\"message\": \"Apex Diagnostics API\", \"status\": \"ok\"}


@api_router.get(\"/health\")
async def health():
    return {\"status\": \"healthy\", \"service\": \"apex-diagnostics\"}


@api_router.post(\"/appointments\", response_model=Appointment, status_code=201)
async def create_appointment(payload: AppointmentCreate):
    try:
        appt = Appointment(**payload.model_dump())
        doc = appt.model_dump()
        doc['created_at'] = doc['created_at'].isoformat()
        await db.appointments.insert_one(doc)
        return appt
    except Exception as e:
        logging.exception(\"Failed to create appointment\")
        raise HTTPException(status_code=500, detail=f\"Failed to create appointment: {str(e)}\")


@api_router.get(\"/appointments\", response_model=List[Appointment])
async def list_appointments():
    items = await db.appointments.find({}, {\"_id\": 0}).sort(\"created_at\", -1).to_list(500)
    for it in items:
        if isinstance(it.get('created_at'), str):
            try:
                it['created_at'] = datetime.fromisoformat(it['created_at'])
            except Exception:
                pass
    return items


# Mount router
app.include_router(api_router)

app.add_middleware(
    CORSMiddleware,
    allow_credentials=True,
    allow_origins=os.environ.get('CORS_ORIGINS', '*').split(','),
    allow_methods=[\"*\"],
    allow_headers=[\"*\"],
)

logging.basicConfig(
    level=logging.INFO,
    format='%(asctime)s - %(name)s - %(levelname)s - %(message)s'
)
logger = logging.getLogger(__name__)


@app.on_event(\"shutdown\")
async def shutdown_db_client():
    client.close()
"
Observation: Overwrite successful: /app/backend/server.py






Now let's build all frontend components in parallel:
Action: file_editor create /app/frontend/src/components/Header.jsx --file-text "import React, { useState, useEffect } from \"react\";
import { motion, AnimatePresence } from \"framer-motion\";
import { List, X, Phone } from \"@phosphor-icons/react\";

const NAV = [
  { label: \"Services\", href: \"#services\" },
  { label: \"Trust\", href: \"#trust\" },
  { label: \"Testimonials\", href: \"#testimonials\" },
  { label: \"Book\", href: \"#book\" },
];

export const Header = () => {
  const [open, setOpen] = useState(false);
  const [scrolled, setScrolled] = useState(false);

  useEffect(() => {
    const onScroll = () => setScrolled(window.scrollY > 20);
    window.addEventListener(\"scroll\", onScroll);
    return () => window.removeEventListener(\"scroll\", onScroll);
  }, []);

  return (
    <header
      data-testid=\"site-header\"
      className={`fixed top-0 inset-x-0 z-50 transition-all duration-300 ${
        scrolled
          ? \"bg-white/85 backdrop-blur-xl backdrop-saturate-150 border-b border-clay-line/60\"
          : \"bg-transparent\"
      }`}
    >
      <div className=\"max-w-7xl mx-auto px-6 lg:px-10 h-20 flex items-center justify-between\">
        <a href=\"#top\" data-testid=\"logo-link\" className=\"flex items-center gap-2.5\">
          <div className=\"w-9 h-9 rounded-full bg-clay-forest flex items-center justify-center\">
            <span className=\"text-clay-bg font-heading font-bold text-lg\">A</span>
          </div>
          <div className=\"leading-tight\">
            <div className=\"font-heading text-[15px] font-semibold tracking-tight text-clay-ink\">Apex Diagnostics</div>
            <div className=\"text-[10px] tracking-[0.18em] uppercase text-clay-mute\">Wellness Clinic</div>
          </div>
        </a>

        <nav className=\"hidden md:flex items-center gap-10\" data-testid=\"primary-nav\">
          {NAV.map((n) => (
            <a
              key={n.href}
              href={n.href}
              data-testid={`nav-${n.label.toLowerCase()}`}
              className=\"text-[14px] font-medium text-clay-ink/80 hover:text-clay-forest transition-colors\"
            >
              {n.label}
            </a>
          ))}
        </nav>

        <div className=\"hidden md:flex items-center gap-3\">
          <a
            href=\"tel:+919876543210\"
            data-testid=\"header-phone-link\"
            className=\"flex items-center gap-2 text-[13px] font-medium text-clay-ink/80 hover:text-clay-forest transition-colors\"
          >
            <Phone size={16} weight=\"duotone\" />
            +91 98765 43210
          </a>
          <a
            href=\"#book\"
            data-testid=\"header-book-cta\"
            className=\"px-5 py-2.5 rounded-full bg-clay-forest text-clay-bg text-[13px] font-semibold hover:bg-clay-forestDark transition-colors\"
          >
            Book Appointment
          </a>
        </div>

        <button
          aria-label=\"Menu\"
          data-testid=\"mobile-menu-toggle\"
          onClick={() => setOpen((o) => !o)}
          className=\"md:hidden w-10 h-10 rounded-full bg-white/90 border border-clay-line flex items-center justify-center\"
        >
          {open ? <X size={18} /> : <List size={18} />}
        </button>
      </div>

      <AnimatePresence>
        {open && (
          <motion.div
            initial={{ opacity: 0, y: -10 }}
            animate={{ opacity: 1, y: 0 }}
            exit={{ opacity: 0, y: -10 }}
            className=\"md:hidden bg-white border-t border-clay-line\"
            data-testid=\"mobile-menu\"
          >
            <div className=\"px-6 py-6 flex flex-col gap-4\">
              {NAV.map((n) => (
                <a
                  key={n.href}
                  href={n.href}
                  onClick={() => setOpen(false)}
                  data-testid={`mobile-nav-${n.label.toLowerCase()}`}
                  className=\"text-sm font-medium text-clay-ink\"
                >
                  {n.label}
                </a>
              ))}
              <a
                href=\"#book\"
                onClick={() => setOpen(false)}
                data-testid=\"mobile-book-cta\"
                className=\"mt-2 px-5 py-3 rounded-full bg-clay-forest text-clay-bg text-sm font-semibold text-center\"
              >
                Book Appointment
              </a>
            </div>
          </motion.div>
        )}
      </AnimatePresence>
    </header>
  );
};
"
Observation: Create successful: /app/frontend/src/components/Header.jsx










Action: file_editor create /app/frontend/src/components/Hero.jsx --file-text "import React from \"react\";
import { motion } from \"framer-motion\";
import { ArrowUpRight, CheckCircle } from \"@phosphor-icons/react\";

const HERO_IMG =
  \"https://images.unsplash.com/photo-1576085898384-b3cdb88736e9?crop=entropy&cs=srgb&fm=jpg&ixid=M3w3NTY2ODh8MHwxfHNlYXJjaHwxfHxtb2Rlcm4lMjBtZWRpY2FsJTIwY2xpbmljJTIwaW50ZXJpb3IlMjBwYXRpZW50fGVufDB8fHx8MTc3OTE3OTYyNHww&ixlib=rb-4.1.0&q=85\";

const fade = {
  hidden: { opacity: 0, y: 24 },
  show: (i = 0) => ({
    opacity: 1,
    y: 0,
    transition: { duration: 0.7, ease: [0.22, 1, 0.36, 1], delay: i * 0.08 },
  }),
};

export const Hero = () => {
  return (
    <section
      id=\"top\"
      data-testid=\"hero-section\"
      className=\"relative pt-32 pb-20 md:pt-40 md:pb-28 overflow-hidden\"
    >
      {/* soft sand background blob */}
      <div className=\"absolute -top-32 -left-32 w-[520px] h-[520px] rounded-full bg-clay-sand blur-3xl opacity-60 pointer-events-none\" />
      <div className=\"absolute top-40 right-0 w-[280px] h-[280px] rounded-full bg-clay-terracotta/15 blur-3xl pointer-events-none\" />

      <div className=\"relative max-w-7xl mx-auto px-6 lg:px-10 grid grid-cols-1 lg:grid-cols-12 gap-12 lg:gap-16 items-center\">
        {/* Left: Text */}
        <div className=\"lg:col-span-6 z-10\">
          <motion.div
            initial=\"hidden\"
            animate=\"show\"
            variants={fade}
            custom={0}
            className=\"inline-flex items-center gap-2 px-3 py-1.5 rounded-full bg-white border border-clay-line\"
          >
            <span className=\"w-1.5 h-1.5 rounded-full bg-clay-terracotta animate-pulse\" />
            <span className=\"text-[11px] tracking-[0.22em] uppercase font-semibold text-clay-forest\">
              Now serving Indiranagar, Bengaluru
            </span>
          </motion.div>

          <motion.h1
            initial=\"hidden\"
            animate=\"show\"
            variants={fade}
            custom={1}
            className=\"mt-6 font-heading text-[44px] leading-[1.02] sm:text-6xl lg:text-[72px] font-medium tracking-tight text-clay-ink\"
          >
            Precise answers,{\" \"}
            <span className=\"italic font-normal text-clay-forest\">
              delivered the same day.
            </span>
          </motion.h1>

          <motion.p
            initial=\"hidden\"
            animate=\"show\"
            variants={fade}
            custom={2}
            className=\"mt-7 max-w-xl text-[17px] leading-relaxed text-clay-mute\"
          >
            A modern diagnostics and wellness clinic built for busy professionals
            and families in Bengaluru &mdash; combining senior consultant
            radiologists, NABL-accredited pathology, and digital reports in your
            inbox before sundown.
          </motion.p>

          <motion.div
            initial=\"hidden\"
            animate=\"show\"
            variants={fade}
            custom={3}
            className=\"mt-9 flex flex-wrap items-center gap-3\"
          >
            <a
              href=\"#book\"
              data-testid=\"hero-schedule-scan-button\"
              className=\"group inline-flex items-center gap-2 px-7 py-4 rounded-full bg-clay-forest text-clay-bg text-[15px] font-semibold hover:bg-clay-forestDark transition-all duration-300 hover:-translate-y-0.5 shadow-[0_8px_30px_rgba(43,92,75,0.18)]\"
            >
              Schedule Your Scan
              <ArrowUpRight size={18} weight=\"bold\" className=\"group-hover:rotate-45 transition-transform\" />
            </a>
            <a
              href=\"#services\"
              data-testid=\"hero-view-packages-button\"
              className=\"inline-flex items-center gap-2 px-7 py-4 rounded-full bg-transparent border border-clay-forest/30 text-clay-forest text-[15px] font-semibold hover:bg-clay-sand transition-all duration-300\"
            >
              View Health Packages
            </a>
          </motion.div>

          {/* Inline trust */}
          <motion.div
            initial=\"hidden\"
            animate=\"show\"
            variants={fade}
            custom={4}
            className=\"mt-12 flex flex-wrap items-center gap-x-7 gap-y-3\"
          >
            {[\"NABL Accredited\", \"Senior Consultant Radiologists\", \"Same-Day Digital Reports\"].map(
              (t) => (
                <div key={t} className=\"flex items-center gap-2\" data-testid={`hero-trust-${t.toLowerCase().replace(/ /g, \"-\")}`}>
                  <CheckCircle size={18} weight=\"duotone\" className=\"text-clay-forest\" />
                  <span className=\"text-[13px] font-medium text-clay-ink/80\">{t}</span>
                </div>
              )
            )}
          </motion.div>
        </div>

        {/* Right: Image */}
        <motion.div
          initial={{ opacity: 0, scale: 0.96 }}
          animate={{ opacity: 1, scale: 1 }}
          transition={{ duration: 1, ease: [0.22, 1, 0.36, 1], delay: 0.3 }}
          className=\"lg:col-span-6 relative\"
        >
          <div className=\"relative rounded-[32px] overflow-hidden aspect-[4/5] lg:aspect-[5/6]\">
            <img
              src={HERO_IMG}
              alt=\"Clean modern clinic interior\"
              className=\"w-full h-full object-cover\"
              loading=\"eager\"
            />
            <div className=\"absolute inset-0 bg-gradient-to-t from-clay-forest/30 via-transparent to-transparent\" />

            {/* Floating card */}
            <div className=\"absolute left-5 right-5 bottom-5 lg:left-6 lg:right-auto lg:bottom-6 lg:max-w-xs bg-white/95 backdrop-blur-md rounded-2xl p-5 border border-white/60 shadow-[0_8px_40px_rgba(0,0,0,0.08)]\">
              <div className=\"flex items-center gap-3\">
                <div className=\"w-10 h-10 rounded-full bg-clay-sand flex items-center justify-center\">
                  <span className=\"font-heading text-clay-forest font-bold text-lg\">24</span>
                </div>
                <div>
                  <div className=\"font-heading text-[15px] font-medium text-clay-ink\">Reports in 24 hours</div>
                  <div className=\"text-[12px] text-clay-mute\">For 92% of all tests booked today</div>
                </div>
              </div>
            </div>
          </div>

          {/* Decorative chip */}
          <div className=\"hidden lg:flex absolute -top-5 -right-3 px-4 py-2 rounded-full bg-clay-ink text-clay-bg text-[11px] tracking-[0.2em] uppercase font-semibold\">
            Est. 2014
          </div>
        </motion.div>
      </div>
    </section>
  );
};
"
Observation: Create successful: /app/frontend/src/components/Hero.jsx








Action: file_editor create /app/frontend/src/components/TrustBadges.jsx --file-text "import React from \"react\";
import { ShieldCheck, UserFocus, ClockCounterClockwise, Microscope, Heartbeat, Lock } from \"@phosphor-icons/react\";

const BADGES = [
  { icon: ShieldCheck, label: \"NABL Accredited Labs\", testid: \"trust-badge-nabl\" },
  { icon: UserFocus, label: \"Senior Consultant Radiologists\", testid: \"trust-badge-radiologists\" },
  { icon: ClockCounterClockwise, label: \"Same-Day Digital Reports\", testid: \"trust-badge-reports\" },
  { icon: Microscope, label: \"Automated Pathology Workflow\", testid: \"trust-badge-pathology\" },
  { icon: Heartbeat, label: \"20,000+ Patients Served\", testid: \"trust-badge-patients\" },
  { icon: Lock, label: \"Encrypted Report Delivery\", testid: \"trust-badge-secure\" },
];

export const TrustBadges = () => {
  // duplicate for seamless marquee
  const items = [...BADGES, ...BADGES];
  return (
    <section id=\"trust\" data-testid=\"trust-badges\" className=\"py-12 md:py-16 border-y border-clay-line bg-white\">
      <div className=\"overflow-hidden\">
        <div className=\"flex gap-16 animate-marquee whitespace-nowrap\" style={{ width: \"max-content\" }}>
          {items.map((b, idx) => {
            const Icon = b.icon;
            return (
              <div
                key={`${b.label}-${idx}`}
                data-testid={idx < BADGES.length ? b.testid : undefined}
                className=\"flex items-center gap-3 shrink-0\"
              >
                <Icon size={22} weight=\"duotone\" className=\"text-clay-forest\" />
                <span className=\"font-heading text-[15px] font-medium text-clay-ink tracking-tight\">
                  {b.label}
                </span>
                <span className=\"text-clay-line ml-12\">/</span>
              </div>
            );
          })}
        </div>
      </div>
    </section>
  );
};
"
Observation: Create successful: /app/frontend/src/components/TrustBadges.jsx




Action: file_editor create /app/frontend/src/components/Services.jsx --file-text "import React from \"react\";
import { motion } from \"framer-motion\";
import { ArrowRight, Check } from \"@phosphor-icons/react\";

const SERVICES = [
  {
    id: \"executive-checkup\",
    eyebrow: \"01 — Preventive Care\",
    title: \"Comprehensive Executive Health Checkups\",
    image:
      \"https://images.unsplash.com/photo-1580489944761-15a19d654956?crop=entropy&cs=srgb&fm=jpg&ixid=M3w4NjAzMjV8MHwxfHNlYXJjaHwxfHxwb3J0cmFpdCUyMGhlYWRzaG90JTIwcHJvZmVzc2lvbmFsJTIwc21pbGluZ3xlbnwwfHx8fDE3NzkxNzk2MjR8MA&ixlib=rb-4.1.0&q=85\",
    description:
      \"Built for demanding schedules &mdash; a complete preventive workup that surfaces silent risk factors years before symptoms appear, reviewed by a senior physician.\",
    included: [
      \"85+ parameter lab profile covering cardiac, metabolic and liver markers\",
      \"Vitals, BMI, ECG and physician-supervised body composition\",
      \"Personalised one-on-one consultation with care plan summary\",
    ],
    cta: \"Book Checkup\",
    serviceValue: \"Executive Health Checkup\",
  },
  {
    id: \"imaging\",
    eyebrow: \"02 — Diagnostic Imaging\",
    title: \"Advanced Diagnostic Imaging (Ultrasound & X-Ray)\",
    image:
      \"https://images.pexels.com/photos/13176356/pexels-photo-13176356.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940\",
    description:
      \"High-resolution ultrasound and digital X-ray, interpreted by senior consultant radiologists to give your doctor a clear, confident diagnosis from the first scan.\",
    included: [
      \"Fully digital imaging with on-screen review at the time of your scan\",
      \"Average wait time under 12 minutes for scheduled appointments\",
      \"Expert reporting by senior radiologists, no junior trainees\",
    ],
    cta: \"Schedule a Scan\",
    serviceValue: \"Diagnostic Imaging (Ultrasound / X-Ray)\",
  },
  {
    id: \"pathology\",
    eyebrow: \"03 — Pathology & Labs\",
    title: \"Specialized Pathology & Blood Labs\",
    image:
      \"https://images.pexels.com/photos/3908179/pexels-photo-3908179.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940\",
    description:
      \"Automated laboratory testing held to NABL standards, with sample logistics designed around you &mdash; from sterile home collection to encrypted digital delivery.\",
    included: [
      \"Sterile, single-use kits with trained phlebotomists at your home\",
      \"Most routine reports processed and dispatched within 6 hours\",
      \"Doctor-friendly report formats with reference ranges and trend lines\",
    ],
    cta: \"Order Lab Test\",
    serviceValue: \"Pathology & Blood Lab\",
  },
];

const SCard = ({ s, i, onSelect }) => (
  <motion.article
    initial={{ opacity: 0, y: 30 }}
    whileInView={{ opacity: 1, y: 0 }}
    viewport={{ once: true, margin: \"-80px\" }}
    transition={{ duration: 0.7, delay: i * 0.1, ease: [0.22, 1, 0.36, 1] }}
    data-testid={`service-card-${s.id}`}
    className=\"group flex flex-col bg-white border border-clay-line rounded-3xl overflow-hidden hover:-translate-y-1 hover:shadow-[0_18px_60px_rgba(0,0,0,0.06)] transition-all duration-500\"
  >
    <div className=\"relative h-56 overflow-hidden\">
      <img
        src={s.image}
        alt={s.title}
        className=\"w-full h-full object-cover group-hover:scale-105 transition-transform duration-700\"
        loading=\"lazy\"
      />
      <div className=\"absolute top-4 left-4 px-3 py-1 rounded-full bg-white/90 backdrop-blur-sm\">
        <span className=\"eyebrow !text-[10px]\">{s.eyebrow}</span>
      </div>
    </div>

    <div className=\"flex-1 flex flex-col p-7 md:p-8\">
      <h3 className=\"font-heading text-[22px] md:text-[24px] leading-tight font-medium tracking-tight text-clay-ink\">
        {s.title}
      </h3>
      <p className=\"mt-3 text-[15px] leading-relaxed text-clay-mute\"
         dangerouslySetInnerHTML={{ __html: s.description }} />

      <ul className=\"mt-6 space-y-3\">
        {s.included.map((item) => (
          <li key={item} className=\"flex gap-3 text-[14px] text-clay-ink/85 leading-snug\">
            <Check size={18} weight=\"bold\" className=\"text-clay-forest mt-0.5 shrink-0\" />
            <span>{item}</span>
          </li>
        ))}
      </ul>

      <button
        onClick={() => onSelect(s.serviceValue)}
        data-testid={`service-cta-${s.id}`}
        className=\"mt-8 self-start inline-flex items-center gap-2 px-6 py-3 rounded-full bg-clay-ink text-clay-bg text-[13px] font-semibold hover:bg-clay-forest transition-colors group/btn\"
      >
        {s.cta}
        <ArrowRight size={16} weight=\"bold\" className=\"group-hover/btn:translate-x-0.5 transition-transform\" />
      </button>
    </div>
  </motion.article>
);

export const Services = ({ onServiceSelect }) => {
  const select = (val) => {
    if (typeof onServiceSelect === \"function\") onServiceSelect(val);
    const el = document.getElementById(\"book\");
    if (el) el.scrollIntoView({ behavior: \"smooth\", block: \"start\" });
  };

  return (
    <section id=\"services\" data-testid=\"services-section\" className=\"relative py-24 md:py-32\">
      <div className=\"max-w-7xl mx-auto px-6 lg:px-10\">
        <div className=\"flex flex-col lg:flex-row lg:items-end lg:justify-between gap-8 mb-14 md:mb-20\">
          <div className=\"max-w-2xl\">
            <span className=\"eyebrow\">What we do</span>
            <h2 className=\"mt-3 font-heading text-4xl sm:text-5xl lg:text-[56px] leading-[1.05] font-medium tracking-tight text-clay-ink\">
              Three pillars of accurate,<br />
              <span className=\"italic font-normal text-clay-forest\">stress-free diagnosis.</span>
            </h2>
          </div>
          <p className=\"max-w-md text-[15px] leading-relaxed text-clay-mute\">
            Every service at Apex is built around a single promise &mdash; the right answer,
            explained clearly, in the shortest possible time.
          </p>
        </div>

        <div className=\"grid grid-cols-1 md:grid-cols-3 gap-6 lg:gap-7\">
          {SERVICES.map((s, i) => (
            <SCard key={s.id} s={s} i={i} onSelect={select} />
          ))}
        </div>
      </div>
    </section>
  );
};
"
Observation: Create successful: /app/frontend/src/components/Services.jsx







Action: file_editor create /app/frontend/src/components/Testimonials.jsx --file-text "import React from \"react\";
import { motion } from \"framer-motion\";
import { Star, Quotes } from \"@phosphor-icons/react\";

const REVIEWS = [
  {
    name: \"Anita Raghavan\",
    role: \"Patient · Indiranagar\",
    avatar:
      \"https://images.unsplash.com/photo-1494790108377-be9c29b29330?crop=entropy&cs=srgb&fm=jpg&ixid=M3w4NjAzMjV8MHwxfHNlYXJjaHwzfHxwb3J0cmFpdCUyMGhlYWRzaG90JTIwcHJvZmVzc2lvbmFsJTIwc21pbGluZ3xlbnwwfHx8fDE3NzkxNzk2MjR8MA&ixlib=rb-4.1.0&q=85\",
    body: \"I came in for an abdominal ultrasound on a Saturday morning and walked out with my digital report in my inbox before lunch. The technician explained every step, the rooms were spotless, and the front desk handled my insurance without making me chase paperwork. Quietly the most professional clinic in Indiranagar.\",
  },
  {
    name: \"Rohan Iyer\",
    role: \"Patient · HSR Layout\",
    avatar:
      \"https://images.unsplash.com/photo-1573497019940-1c28c88b4f3e?crop=entropy&cs=srgb&fm=jpg&ixid=M3w4NjAzMjV8MHwxfHNlYXJjaHwyfHxwb3J0cmFpdCUyMGhlYWRzaG90JTIwcHJvZmVzc2lvbmFsJTIwc21pbGluZ3xlbnwwfHx8fDE3NzkxNzk2MjR8MA&ixlib=rb-4.1.0&q=85\",
    body: \"Booked an executive health checkup for my mother. The phlebotomist arrived at 7 AM as promised, the home collection was painless, and the reports were uploaded by 4 PM the same day. The consulting physician actually sat with us for forty minutes to walk through the findings. Worth every rupee.\",
  },
];

export const Testimonials = () => {
  return (
    <section id=\"testimonials\" data-testid=\"testimonials-section\" className=\"py-24 md:py-32 bg-clay-sand/40\">
      <div className=\"max-w-7xl mx-auto px-6 lg:px-10\">
        <div className=\"flex flex-col md:flex-row md:items-end md:justify-between gap-6 mb-14\">
          <div>
            <span className=\"eyebrow\">Social proof</span>
            <h2 className=\"mt-3 font-heading text-4xl sm:text-5xl lg:text-[52px] font-medium tracking-tight text-clay-ink leading-[1.05]\">
              What our patients say
            </h2>
          </div>
          <div className=\"flex items-center gap-3\">
            <div className=\"flex gap-0.5\">
              {[1, 2, 3, 4, 5].map((n) => (
                <Star key={n} size={20} weight=\"fill\" className=\"text-clay-terracotta\" />
              ))}
            </div>
            <span className=\"text-[14px] font-medium text-clay-ink\">4.9 / 5 across 1,200+ reviews</span>
          </div>
        </div>

        <div className=\"grid grid-cols-1 md:grid-cols-2 gap-6 md:gap-8\">
          {REVIEWS.map((r, i) => (
            <motion.figure
              key={r.name}
              initial={{ opacity: 0, y: 24 }}
              whileInView={{ opacity: 1, y: 0 }}
              viewport={{ once: true, margin: \"-60px\" }}
              transition={{ duration: 0.6, delay: i * 0.1, ease: [0.22, 1, 0.36, 1] }}
              data-testid={`testimonial-card-${i + 1}`}
              className=\"relative bg-white border border-clay-line rounded-3xl p-8 md:p-10\"
            >
              <Quotes size={36} weight=\"fill\" className=\"text-clay-sand absolute top-7 right-7\" />
              <blockquote className=\"font-heading text-[19px] md:text-[20px] leading-[1.55] text-clay-ink font-normal tracking-tight\">
                &ldquo;{r.body}&rdquo;
              </blockquote>
              <figcaption className=\"mt-7 flex items-center gap-4\">
                <img
                  src={r.avatar}
                  alt={r.name}
                  className=\"w-12 h-12 rounded-full object-cover\"
                  loading=\"lazy\"
                />
                <div>
                  <div className=\"font-heading text-[15px] font-semibold text-clay-ink\">{r.name}</div>
                  <div className=\"text-[12px] text-clay-mute tracking-wide\">{r.role}</div>
                </div>
              </figcaption>
            </motion.figure>
          ))}
        </div>
      </div>
    </section>
  );
};
"
Observation: Create successful: /app/frontend/src/components/Testimonials.jsx


Action: file_editor create /app/frontend/src/components/AppointmentSection.jsx --file-text "import React, { useState } from \"react\";
import axios from \"axios\";
import { motion } from \"framer-motion\";
import { toast } from \"sonner\";
import { Phone, MapPin, ArrowRight, CheckCircle, CalendarBlank } from \"@phosphor-icons/react\";

const BACKEND_URL = process.env.REACT_APP_BACKEND_URL;
const API = `${BACKEND_URL}/api`;

const SERVICE_OPTIONS = [
  \"Executive Health Checkup\",
  \"Diagnostic Imaging (Ultrasound / X-Ray)\",
  \"Pathology & Blood Lab\",
  \"General Consultation\",
];

export const AppointmentSection = ({ selectedService, onSelectedServiceUsed }) => {
  const [form, setForm] = useState({
    full_name: \"\",
    phone: \"\",
    email: \"\",
    service: selectedService || SERVICE_OPTIONS[0],
    preferred_date: \"\",
    preferred_time: \"\",
    message: \"\",
  });
  const [submitting, setSubmitting] = useState(false);
  const [success, setSuccess] = useState(false);

  // Sync selectedService when changed externally
  React.useEffect(() => {
    if (selectedService) {
      setForm((f) => ({ ...f, service: selectedService }));
      if (typeof onSelectedServiceUsed === \"function\") onSelectedServiceUsed();
    }
    // eslint-disable-next-line react-hooks/exhaustive-deps
  }, [selectedService]);

  const handle = (k) => (e) => setForm({ ...form, [k]: e.target.value });

  const submit = async (e) => {
    e.preventDefault();
    if (!form.full_name.trim() || !form.phone.trim() || !form.service) {
      toast.error(\"Please fill in your name, phone, and choose a service.\");
      return;
    }
    setSubmitting(true);
    try {
      const payload = { ...form };
      if (!payload.email) delete payload.email;
      if (!payload.preferred_date) delete payload.preferred_date;
      if (!payload.preferred_time) delete payload.preferred_time;
      if (!payload.message) delete payload.message;

      await axios.post(`${API}/appointments`, payload);
      setSuccess(true);
      toast.success(\"Appointment request received. We'll call you shortly.\");
      setForm({
        full_name: \"\",
        phone: \"\",
        email: \"\",
        service: SERVICE_OPTIONS[0],
        preferred_date: \"\",
        preferred_time: \"\",
        message: \"\",
      });
    } catch (err) {
      console.error(err);
      const detail = err?.response?.data?.detail || \"Something went wrong. Please call us.\";
      toast.error(typeof detail === \"string\" ? detail : \"Could not submit. Please try again.\");
    } finally {
      setSubmitting(false);
    }
  };

  return (
    <section id=\"book\" data-testid=\"appointment-section\" className=\"relative py-24 md:py-32 bg-clay-forest text-clay-bg overflow-hidden\">
      <div className=\"absolute -top-40 -right-40 w-[480px] h-[480px] rounded-full bg-clay-terracotta/20 blur-3xl pointer-events-none\" />
      <div className=\"absolute -bottom-40 -left-40 w-[480px] h-[480px] rounded-full bg-clay-forestDark blur-3xl pointer-events-none\" />

      <div className=\"relative max-w-7xl mx-auto px-6 lg:px-10 grid grid-cols-1 lg:grid-cols-12 gap-12 lg:gap-16\">
        <motion.div
          initial={{ opacity: 0, y: 24 }}
          whileInView={{ opacity: 1, y: 0 }}
          viewport={{ once: true }}
          transition={{ duration: 0.7, ease: [0.22, 1, 0.36, 1] }}
          className=\"lg:col-span-5\"
        >
          <span className=\"eyebrow !text-clay-sand\">Prioritize your health today</span>
          <h2 className=\"mt-4 font-heading text-4xl sm:text-5xl lg:text-[56px] font-medium leading-[1.05] tracking-tight\">
            Early detection is the most decisive medicine.
          </h2>
          <p className=\"mt-6 text-[16px] leading-relaxed text-clay-bg/80 max-w-md\">
            Most serious conditions reveal themselves quietly long before symptoms arrive.
            A thirty-minute appointment at our Indiranagar clinic could be the most
            important meeting on your calendar this quarter.
          </p>

          <div className=\"mt-10 space-y-5\">
            <div className=\"flex items-start gap-4\">
              <div className=\"w-11 h-11 rounded-full bg-white/10 flex items-center justify-center shrink-0\">
                <MapPin size={20} weight=\"duotone\" />
              </div>
              <div>
                <div className=\"font-heading text-[15px] font-medium\">Apex Diagnostics & Wellness Clinic</div>
                <div className=\"text-[13px] text-clay-bg/70 mt-0.5\">
                  100 Feet Road, Indiranagar, Bengaluru 560038
                </div>
              </div>
            </div>
            <div className=\"flex items-start gap-4\">
              <div className=\"w-11 h-11 rounded-full bg-white/10 flex items-center justify-center shrink-0\">
                <Phone size={20} weight=\"duotone\" />
              </div>
              <div>
                <div className=\"font-heading text-[15px] font-medium\">Or call us directly</div>
                <a href=\"tel:+919876543210\" data-testid=\"banner-phone-link\" className=\"text-[13px] text-clay-bg/70 hover:text-clay-bg block mt-0.5\">
                  +91 98765 43210 &middot; Walk-ins welcome
                </a>
                <a href=\"tel:+919876543211\" className=\"text-[13px] text-clay-bg/70 hover:text-clay-bg block\">
                  +91 98765 43211 &middot; Emergencies (24x7)
                </a>
              </div>
            </div>
            <div className=\"flex items-start gap-4\">
              <div className=\"w-11 h-11 rounded-full bg-white/10 flex items-center justify-center shrink-0\">
                <CalendarBlank size={20} weight=\"duotone\" />
              </div>
              <div>
                <div className=\"font-heading text-[15px] font-medium\">Operating hours</div>
                <div className=\"text-[13px] text-clay-bg/70 mt-0.5\">
                  Mon &ndash; Sat &middot; 7:00 AM &ndash; 9:00 PM &nbsp;|&nbsp; Sun &middot; 8:00 AM &ndash; 2:00 PM
                </div>
              </div>
            </div>
          </div>
        </motion.div>

        {/* Form card */}
        <motion.div
          initial={{ opacity: 0, y: 24 }}
          whileInView={{ opacity: 1, y: 0 }}
          viewport={{ once: true }}
          transition={{ duration: 0.7, delay: 0.1, ease: [0.22, 1, 0.36, 1] }}
          className=\"lg:col-span-7\"
        >
          <div className=\"bg-clay-bg text-clay-ink rounded-[28px] p-7 md:p-10 shadow-[0_30px_80px_rgba(0,0,0,0.18)]\">
            {success ? (
              <div data-testid=\"appointment-success\" className=\"py-10 text-center\">
                <div className=\"w-16 h-16 rounded-full bg-clay-forest/10 mx-auto flex items-center justify-center\">
                  <CheckCircle size={36} weight=\"duotone\" className=\"text-clay-forest\" />
                </div>
                <h3 className=\"mt-6 font-heading text-2xl font-medium text-clay-ink\">Request received</h3>
                <p className=\"mt-3 text-[15px] text-clay-mute max-w-md mx-auto\">
                  Our care coordinator will call you within the next 30 minutes to confirm your appointment slot.
                </p>
                <button
                  onClick={() => setSuccess(false)}
                  data-testid=\"appointment-book-another\"
                  className=\"mt-8 inline-flex items-center gap-2 px-6 py-3 rounded-full bg-clay-forest text-clay-bg text-[13px] font-semibold hover:bg-clay-forestDark\"
                >
                  Book another <ArrowRight size={16} weight=\"bold\" />
                </button>
              </div>
            ) : (
              <form onSubmit={submit} data-testid=\"appointment-form\" className=\"space-y-5\">
                <div>
                  <h3 className=\"font-heading text-[26px] font-medium tracking-tight text-clay-ink\">
                    Book an appointment online
                  </h3>
                  <p className=\"text-[13px] text-clay-mute mt-1\">
                    Fill in your details. We&apos;ll confirm within 30 minutes.
                  </p>
                </div>

                <div className=\"grid grid-cols-1 sm:grid-cols-2 gap-4\">
                  <Field label=\"Full name\">
                    <input
                      data-testid=\"appointment-input-name\"
                      value={form.full_name}
                      onChange={handle(\"full_name\")}
                      required
                      type=\"text\"
                      placeholder=\"e.g. Priya Sharma\"
                      className={inputCls}
                    />
                  </Field>
                  <Field label=\"Phone\">
                    <input
                      data-testid=\"appointment-input-phone\"
                      value={form.phone}
                      onChange={handle(\"phone\")}
                      required
                      type=\"tel\"
                      placeholder=\"+91 98765 43210\"
                      className={inputCls}
                    />
                  </Field>
                  <Field label=\"Email (optional)\">
                    <input
                      data-testid=\"appointment-input-email\"
                      value={form.email}
                      onChange={handle(\"email\")}
                      type=\"email\"
                      placeholder=\"you@email.com\"
                      className={inputCls}
                    />
                  </Field>
                  <Field label=\"Service\">
                    <select
                      data-testid=\"appointment-input-service\"
                      value={form.service}
                      onChange={handle(\"service\")}
                      className={inputCls}
                    >
                      {SERVICE_OPTIONS.map((s) => (
                        <option key={s} value={s}>{s}</option>
                      ))}
                    </select>
                  </Field>
                  <Field label=\"Preferred date\">
                    <input
                      data-testid=\"appointment-input-date\"
                      value={form.preferred_date}
                      onChange={handle(\"preferred_date\")}
                      type=\"date\"
                      className={inputCls}
                    />
                  </Field>
                  <Field label=\"Preferred time\">
                    <input
                      data-testid=\"appointment-input-time\"
                      value={form.preferred_time}
                      onChange={handle(\"preferred_time\")}
                      type=\"time\"
                      className={inputCls}
                    />
                  </Field>
                </div>

                <Field label=\"Anything we should know? (optional)\">
                  <textarea
                    data-testid=\"appointment-input-message\"
                    value={form.message}
                    onChange={handle(\"message\")}
                    rows={3}
                    placeholder=\"Past medical history, prescription notes, etc.\"
                    className={`${inputCls} resize-none`}
                  />
                </Field>

                <button
                  type=\"submit\"
                  disabled={submitting}
                  data-testid=\"appointment-submit-button\"
                  className=\"w-full sm:w-auto inline-flex items-center justify-center gap-2 px-8 py-4 rounded-full bg-clay-forest text-clay-bg text-[14px] font-semibold hover:bg-clay-forestDark disabled:opacity-60 transition-colors\"
                >
                  {submitting ? \"Booking...\" : \"Book an Appointment Online\"}
                  <ArrowRight size={16} weight=\"bold\" />
                </button>

                <p className=\"text-[11px] text-clay-mute pt-2\">
                  By submitting, you agree to receive a confirmation call. Your information is kept private and encrypted.
                </p>
              </form>
            )}
          </div>
        </motion.div>
      </div>
    </section>
  );
};

const inputCls =
  \"w-full px-4 py-3 rounded-xl bg-white border border-clay-line text-[14px] text-clay-ink placeholder:text-clay-mute/70 focus:outline-none focus:border-clay-forest focus:ring-2 focus:ring-clay-forest/15 transition-all\";

const Field = ({ label, children }) => (
  <label className=\"block\">
    <span className=\"block text-[11px] tracking-[0.18em] uppercase font-semibold text-clay-forest mb-1.5\">
      {label}
    </span>
    {children}
  </label>
);
"
Observation: Create successful: /app/frontend/src/components/AppointmentSection.jsx





Action: file_editor create /app/frontend/src/components/Footer.jsx --file-text "import React from \"react\";
import { Phone, EnvelopeSimple, MapPin, InstagramLogo, FacebookLogo, LinkedinLogo } from \"@phosphor-icons/react\";

export const Footer = () => {
  return (
    <footer data-testid=\"site-footer\" className=\"bg-clay-bg border-t border-clay-line pt-20 pb-10\">
      <div className=\"max-w-7xl mx-auto px-6 lg:px-10\">
        <div className=\"grid grid-cols-1 md:grid-cols-12 gap-10 md:gap-14\">
          <div className=\"md:col-span-5\">
            <div className=\"flex items-center gap-2.5\">
              <div className=\"w-10 h-10 rounded-full bg-clay-forest flex items-center justify-center\">
                <span className=\"text-clay-bg font-heading font-bold text-lg\">A</span>
              </div>
              <div className=\"leading-tight\">
                <div className=\"font-heading text-[16px] font-semibold tracking-tight text-clay-ink\">Apex Diagnostics</div>
                <div className=\"text-[10px] tracking-[0.18em] uppercase text-clay-mute\">Wellness Clinic</div>
              </div>
            </div>
            <p className=\"mt-6 text-[14px] leading-relaxed text-clay-mute max-w-md\">
              A modern diagnostics and preventive wellness practice serving Bengaluru since 2014.
              Precise answers, kind people, same-day reports.
            </p>
            <div className=\"mt-6 flex items-center gap-3\">
              <SocialLink href=\"#\" testid=\"footer-social-instagram\"><InstagramLogo size={18} weight=\"duotone\" /></SocialLink>
              <SocialLink href=\"#\" testid=\"footer-social-facebook\"><FacebookLogo size={18} weight=\"duotone\" /></SocialLink>
              <SocialLink href=\"#\" testid=\"footer-social-linkedin\"><LinkedinLogo size={18} weight=\"duotone\" /></SocialLink>
            </div>
          </div>

          <div className=\"md:col-span-3\">
            <div className=\"eyebrow\">Services</div>
            <ul className=\"mt-4 space-y-2.5 text-[14px] text-clay-ink/80\">
              <li><a href=\"#services\" className=\"hover:text-clay-forest\">Executive Health Checkups</a></li>
              <li><a href=\"#services\" className=\"hover:text-clay-forest\">Ultrasound &amp; X-Ray</a></li>
              <li><a href=\"#services\" className=\"hover:text-clay-forest\">Pathology &amp; Blood Labs</a></li>
              <li><a href=\"#services\" className=\"hover:text-clay-forest\">Home Sample Collection</a></li>
            </ul>
          </div>

          <div className=\"md:col-span-4\">
            <div className=\"eyebrow\">Visit / Contact</div>
            <ul className=\"mt-4 space-y-3 text-[14px] text-clay-ink/85\">
              <li className=\"flex gap-3\">
                <MapPin size={18} weight=\"duotone\" className=\"text-clay-forest mt-0.5 shrink-0\" />
                100 Feet Road, Indiranagar, Bengaluru 560038
              </li>
              <li className=\"flex gap-3\">
                <Phone size={18} weight=\"duotone\" className=\"text-clay-forest mt-0.5 shrink-0\" />
                <a href=\"tel:+919876543210\" data-testid=\"footer-phone\" className=\"hover:text-clay-forest\">+91 98765 43210</a>
              </li>
              <li className=\"flex gap-3\">
                <EnvelopeSimple size={18} weight=\"duotone\" className=\"text-clay-forest mt-0.5 shrink-0\" />
                <a href=\"mailto:care@apexdiagnostics.in\" data-testid=\"footer-email\" className=\"hover:text-clay-forest\">care@apexdiagnostics.in</a>
              </li>
            </ul>
          </div>
        </div>

        <div className=\"mt-16 pt-8 border-t border-clay-line flex flex-col md:flex-row items-start md:items-center justify-between gap-4\">
          <div className=\"text-[12px] text-clay-mute\">
            &copy; {new Date().getFullYear()} Apex Diagnostics & Wellness Clinic. All rights reserved.
          </div>
          <div className=\"flex items-center gap-6 text-[12px] text-clay-mute\">
            <a href=\"#\" className=\"hover:text-clay-forest\">Privacy Policy</a>
            <a href=\"#\" className=\"hover:text-clay-forest\">Terms</a>
            <a href=\"#\" className=\"hover:text-clay-forest\">NABL Certificate</a>
          </div>
        </div>
      </div>
    </footer>
  );
};

const SocialLink = ({ href, children, testid }) => (
  <a
    href={href}
    data-testid={testid}
    className=\"w-10 h-10 rounded-full border border-clay-line bg-white flex items-center justify-center text-clay-forest hover:bg-clay-sand transition-colors\"
  >
    {children}
  </a>
);
"
Observation: Create successful: /app/frontend/src/components/Footer.jsx
>






Action: file_editor create /app/frontend/src/App.js --file-text "import React, { useState } from \"react\";
import \"@/App.css\";
import { BrowserRouter, Routes, Route } from \"react-router-dom\";
import { Toaster } from \"sonner\";

import { Header } from \"./components/Header\";
import { Hero } from \"./components/Hero\";
import { TrustBadges } from \"./components/TrustBadges\";
import { Services } from \"./components/Services\";
import { Testimonials } from \"./components/Testimonials\";
import { AppointmentSection } from \"./components/AppointmentSection\";
import { Footer } from \"./components/Footer\";

const Home = () => {
  const [selectedService, setSelectedService] = useState(null);

  return (
    <main data-testid=\"home-page\" className=\"bg-clay-bg text-clay-ink min-h-screen\">
      <Header />
      <Hero />
      <TrustBadges />
      <Services onServiceSelect={setSelectedService} />
      <Testimonials />
      <AppointmentSection
        selectedService={selectedService}
        onSelectedServiceUsed={() => setSelectedService(null)}
      />
      <Footer />
    </main>
  );
};

function App() {
  return (
    <div className=\"App\">
      <BrowserRouter>
        <Toaster richColors position=\"top-center\" />
        <Routes>
          <Route path=\"/\" element={<Home />} />
        </Routes>
      </BrowserRouter>
    </div>
  );
}

export default App;
"
Observation: Overwrite successful: /app/frontend/src/App.js



















<img width="1920" height="1080" alt="image-1" src="https://github.com/user-attachments/assets/6ca24a88-758d-4aa6-8d1c-24271defed3d" />
