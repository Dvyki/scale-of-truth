import { useState } from "react";
import { motion } from "framer-motion";
import { FaFacebookF, FaInstagram, FaTwitter, FaLinkedin } from "react-icons/fa";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";

const gatorAnimations = [
  { rotate: 0, scale: 1 },
  { rotate: 15, scale: 1.1 },
  { rotate: -15, scale: 1.2 },
  { rotate: 0, scale: 0.9 },
];

export default function HomePage() {
  const [gatorIndex, setGatorIndex] = useState(0);

  const handleGatorClick = () => {
    setGatorIndex((prev) => (prev + 1) % gatorAnimations.length);
  };

  return (
    <div className="min-h-screen bg-white text-gray-800">
      {/* Navbar */}
      <header className="flex justify-between items-center p-6 shadow-md">
        <h1 className="text-2xl font-bold">GatorMedia</h1>
        <nav className="flex space-x-6">
          <a href="#home" className="hover:underline">Ana Sayfa</a>
          <a href="#about" className="hover:underline">Hakkımızda</a>
          <a href="#services" className="hover:underline">Hizmetler</a>
          <a href="#contact" className="hover:underline">İletişim</a>
        </nav>
      </header>

      {/* Hero Section */}
      <section id="home" className="text-center py-20 bg-gradient-to-b from-blue-100 to-white">
        <h2 className="text-4xl font-extrabold mb-4">Sosyal Medya Ajansınız</h2>
        <p className="mb-8 text-lg max-w-xl mx-auto">
          GatorMedia ile dijital dünyada fark yaratın! Stratejik içerikler, yaratıcı kampanyalar ve etkili sosyal medya yönetimi.
        </p>
        <Button className="text-white bg-blue-600 hover:bg-blue-700">Bizimle Çalışın</Button>
        <motion.div
          className="mt-10 mx-auto w-48 h-48 cursor-pointer"
          animate={gatorAnimations[gatorIndex]}
          transition={{ duration: 0.5 }}
          onClick={handleGatorClick}
        >
          <img src="/gator.png" alt="Gator Mascot" className="w-full h-full object-contain" />
        </motion.div>
      </section>

      {/* About Section */}
      <section id="about" className="py-20 px-6 bg-gray-50">
        <h3 className="text-3xl font-bold mb-6 text-center">Hakkımızda</h3>
        <p className="max-w-3xl mx-auto text-center text-lg">
          GatorMedia, markanızı dijitalde büyütmek için yaratıcı çözümler sunan bir sosyal medya ajansıdır. Deneyimli ekibimizle her zaman bir adım öndesiniz.
        </p>
      </section>

      {/* Services Section */}
      <section id="services" className="py-20 px-6">
        <h3 className="text-3xl font-bold mb-10 text-center">Hizmetlerimiz</h3>
        <div className="grid grid-cols-1 md:grid-cols-3 gap-6 max-w-5xl mx-auto">
          <Card>
            <CardContent>
              <h4 className="text-xl font-semibold mb-2">İçerik Üretimi</h4>
              <p>Markanıza özel etkili sosyal medya içerikleri üretiriz.</p>
            </CardContent>
          </Card>
          <Card>
            <CardContent>
              <h4 className="text-xl font-semibold mb-2">Reklam Yönetimi</h4>
              <p>Hedef kitlenize ulaşan reklam kampanyaları tasarlarız.</p>
            </CardContent>
          </Card>
          <Card>
            <CardContent>
              <h4 className="text-xl font-semibold mb-2">Raporlama & Analiz</h4>
              <p>Veriye dayalı analizlerle stratejilerinizi optimize ederiz.</p>
            </CardContent>
          </Card>
        </div>
      </section>

      {/* Contact Section */}
      <section id="contact" className="py-20 px-6 bg-gray-100">
        <h3 className="text-3xl font-bold mb-6 text-center">İletişim</h3>
        <div className="flex flex-col items-center space-y-4">
          <p>info@gatormedia.com</p>
          <p>+90 212 123 45 67</p>
          <div className="flex space-x-4 text-xl">
            <a href="#"><FaFacebookF /></a>
            <a href="#"><FaInstagram /></a>
            <a href="#"><FaTwitter /></a>
            <a href="#"><FaLinkedin /></a>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="text-center py-6 bg-white border-t">
        <p>&copy; 2025 GatorMedia. Tüm hakları saklıdır.</p>
      </footer>
    </div>
  );
}
