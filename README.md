# kanza-audit
Página web comercial para empresa  KANSA AUDIT 
kanza-audit/
│── src/
│   ├── pages/
│   │   ├── index.jsx         # Landing Page
│   │   ├── login.jsx         # Inicio de sesión
│   │   ├── register.jsx      # Registro
│   │   ├── dashboard.jsx     # Zona privada
│   ├── components/
│   │   ├── Navbar.jsx
│   │   ├── Footer.jsx
│   │   ├── ServiceCard.jsx
│   ├── lib/
│   │   └── supabaseClient.js
│── package.json
│── tailwind.config.js
│── postcss.config.js
│── index.html
import { createClient } from '@supabase/supabase-js'

const supabaseUrl = import.meta.env.VITE_SUPABASE_URL
const supabaseKey = import.meta.env.VITE_SUPABASE_ANON_KEY

export const supabase = createClient(supabaseUrl, supabaseKey)
export default function Navbar() {
  return (
    <nav className="bg-[#0B1F3A] text-white shadow-lg">
      <div className="max-w-7xl mx-auto px-6 py-4 flex justify-between items-center">
        <h1 className="text-2xl font-bold text-[#D4AF37]">KANZA AUDIT</h1>
        <div className="space-x-6">
          <a href="/" className="hover:text-[#D4AF37]">Inicio</a>
          <a href="/login" className="hover:text-[#D4AF37]">Clientes</a>
          <a href="/register" className="hover:text-[#D4AF37]">Registro</a>
        </div>
      </div>
    </nav>
  )
}
import Navbar from "../components/Navbar"

export default function Home() {
  return (
    <div>
      <Navbar />
      <section className="bg-gradient-to-r from-[#0B1F3A] via-[#183153] to-[#102A44] text-white min-h-screen flex flex-col items-center justify-center px-6">
        <h1 className="text-5xl font-bold text-[#D4AF37] mb-6">KANZA AUDIT</h1>
        <p className="max-w-2xl text-lg text-center">
          Somos una firma contable especializada en <span className="text-[#28A745] font-semibold">Auditoría, Contabilidad, Declaraciones de Renta</span> y más.
        </p>
        <div className="mt-10 flex gap-6">
          <a href="/login" className="bg-[#28A745] text-white px-6 py-3 rounded-xl shadow-lg hover:bg-[#218838]">Acceso Clientes</a>
          <a href="/register" className="bg-[#D4AF37] text-black px-6 py-3 rounded-xl shadow-lg hover:bg-yellow-600">Regístrate</a>
        </div>
      </section>
    </div>
  )
}
