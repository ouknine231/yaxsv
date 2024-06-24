import React, { useState } from 'react';
import { Camera } from 'lucide-react';

const pages = {
  home: {
    title: "الصفحة الرئيسية",
    content: "مرحبًا بكم في موقعنا! نحن نقدم خدمات مميزة لعملائنا الكرام."
  },
  about: {
    title: "من نحن",
    content: "نحن شركة رائدة في مجالنا، نسعى دائمًا لتقديم أفضل الخدمات لعملائنا."
  },
  services: {
    title: "خدماتنا",
    content: "نقدم مجموعة واسعة من الخدمات المتميزة لتلبية احتياجاتكم."
  },
  contact: {
    title: "اتصل بنا",
    content: "يمكنكم التواصل معنا عبر البريد الإلكتروني أو الهاتف للاستفسارات والطلبات."
  }
};

const WebsitePreview = () => {
  const [currentPage, setCurrentPage] = useState('home');

  return (
    <div className="bg-gradient-to-r from-purple-500 to-indigo-600 min-h-screen flex flex-col text-white">
      <header className="bg-white bg-opacity-10 p-4">
        <div className="container mx-auto flex justify-between items-center">
          <div className="flex items-center">
            <Camera size={32} className="text-yellow-300 mr-2" />
            <span className="text-2xl font-bold">شعارنا</span>
          </div>
          <nav>
            {Object.keys(pages).map((page) => (
              <button
                key={page}
                onClick={() => setCurrentPage(page)}
                className={`mx-2 py-2 px-4 rounded transition duration-300 ${
                  currentPage === page ? 'bg-white text-purple-600' : 'hover:bg-white hover:bg-opacity-20'
                }`}
              >
                {pages[page].title}
              </button>
            ))}
          </nav>
        </div>
      </header>
      <main className="flex-grow container mx-auto p-8">
        <div className="bg-white bg-opacity-10 p-8 rounded-lg shadow-lg">
          <h1 className="text-3xl font-bold mb-4 text-right">{pages[currentPage].title}</h1>
          <p className="text-lg text-right">{pages[currentPage].content}</p>
        </div>
      </main>
      <footer className="bg-white bg-opacity-10 p-4 text-center">
        <p>جميع الحقوق محفوظة © 2024</p>
      </footer>
    </div>
  );
};

export default WebsitePreview;
