import React, { useState } from "react";
import { Button } from "@/components/ui/button";
import { Card, CardContent } from "@/components/ui/card";
import { Input } from "@/components/ui/input";

export default function HomePage() {
  const [showMockTest, setShowMockTest] = useState(false);
  const handleMockTestClick = () => {
    setShowMockTest(true);
    const section = document.getElementById("mocktest");
    if (section) section.scrollIntoView({ behavior: "smooth" });
  };

  return (
    <div className="min-h-screen bg-gradient-to-b from-white to-blue-50 font-sans">
      {/* Header Navigation */}
      <header className="bg-white shadow-md py-4 px-6 flex justify-between items-center">
        <h1 className="text-2xl font-bold text-blue-700">TNPSC Academy</h1>
        <nav className="flex gap-6 text-sm font-medium">
          <a href="#" className="text-blue-700 hover:text-blue-900">Home</a>
          <a href="#" className="text-blue-700 hover:text-blue-900">Paid Course</a>
          <a href="#mocktest" className="text-blue-700 hover:text-blue-900" onClick={handleMockTestClick}>Mock Test</a>
          <a href="#" className="text-blue-700 hover:text-blue-900">Free Video</a>
          <a href="#pyq" className="text-blue-700 hover:text-blue-900">PYQ</a>
        </nav>
      </header>

      {/* Main content */}
      <div>
        <section className="bg-gradient-to-r from-blue-800 to-blue-600 text-white py-20 px-6 text-center">
          <h2 className="text-4xl font-bold mb-4">Prepare for TNPSC Exams with Experts</h2>
          <p className="text-lg max-w-2xl mx-auto mb-6">Join our complete TNPSC preparation platform including video lectures, mock tests, notes, and PYQs – all in one place.</p>
          <Button className="bg-white text-blue-700 font-bold px-6 py-2 rounded-full hover:bg-blue-100">Join Now</Button>
        </section>

        <section className="py-16 px-4 max-w-7xl mx-auto grid grid-cols-1 md:grid-cols-3 gap-10">
          <Card className="rounded-2xl shadow-xl border border-blue-100">
            <CardContent className="p-8 text-center">
              <h3 className="text-2xl font-bold text-blue-700 mb-2">Paid Course</h3>
              <p className="text-gray-600 mb-4">Structured syllabus with chapter-wise video classes by subject experts.</p>
              <Button className="bg-blue-700 hover:bg-blue-800 text-white px-6">Join Now</Button>
            </CardContent>
          </Card>

          <Card className="rounded-2xl shadow-xl border border-blue-100">
            <CardContent className="p-8 text-center">
              <h3 className="text-2xl font-bold text-blue-700 mb-2">Mock Test</h3>
              <p className="text-gray-600 mb-4">Topic-wise and full-length TNPSC mock tests with instant results.</p>
              <Button onClick={handleMockTestClick} className="bg-blue-700 hover:bg-blue-800 text-white px-6">Start Now</Button>
            </CardContent>
          </Card>

          <Card className="rounded-2xl shadow-xl border border-blue-100">
            <CardContent className="p-8 text-center">
              <h3 className="text-2xl font-bold text-blue-700 mb-2">Free Video</h3>
              <p className="text-gray-600 mb-4">Watch free topic-wise classes to boost your basics and revise easily.</p>
              <Button className="bg-blue-700 hover:bg-blue-800 text-white px-6">Watch Now</Button>
            </CardContent>
          </Card>

          <Card id="pyq" className="rounded-2xl shadow-xl border border-blue-100 col-span-1 md:col-span-3">
            <CardContent className="p-8 text-center">
              <h3 className="text-2xl font-bold text-blue-700 mb-2">Previous Year Questions (PYQ)</h3>
              <p className="text-gray-600 mb-4">Download and solve past year TNPSC papers with detailed answers.</p>
              <Button className="bg-blue-700 hover:bg-blue-800 text-white px-6">Download Now</Button>
              <div className="mt-10 text-left">
                <h4 className="text-xl font-semibold text-blue-700 mb-4">Subject-wise PYQ</h4>
                <ul className="list-disc list-inside text-gray-700">
                  <li><a href="#">History</a></li>
                  <li><a href="#">Polity</a></li>
                  <li><a href="#">Geography</a></li>
                  <li><a href="#">Economy</a></li>
                  <li><a href="#">Science</a></li>
                  <li><a href="#">Current Affairs</a></li>
                  <li><a href="#">General English</a></li>
                  <li><a href="#">Aptitude & Mental Ability</a></li>
                </ul>
              </div>
            </CardContent>
          </Card>
        </section>

        {showMockTest && (
          <section id="mocktest" className="py-16 px-6">
            <div className="max-w-4xl mx-auto bg-white rounded-2xl p-10 shadow-xl">
              <h4 className="text-3xl font-bold text-center text-blue-700 mb-6">Mock Test - TNPSC Subjects</h4>
              <ul className="list-disc list-inside text-gray-700">
                <li><a href="#">History Questions</a></li>
                <li><a href="#">Polity Questions</a></li>
                <li><a href="#">Geography Questions</a></li>
                <li><a href="#">Economy Questions</a></li>
                <li><a href="#">Science Questions</a></li>
                <li><a href="#">Current Affairs Questions</a></li>
                <li><a href="#">General English Questions</a></li>
                <li><a href="#">Aptitude & Mental Ability Questions</a></li>
              </ul>
            </div>
          </section>
        )}

        <section className="bg-white py-16 px-6">
          <div className="max-w-4xl mx-auto bg-blue-50 rounded-2xl p-10 shadow-xl">
            <h4 className="text-3xl font-bold text-center text-blue-700 mb-6">Enquiry Form</h4>
            <form className="grid grid-cols-1 md:grid-cols-2 gap-6">
              <Input placeholder="Name" className="border-gray-300 focus:ring-blue-500" />
              <Input placeholder="Email" className="border-gray-300 focus:ring-blue-500" />
              <Input placeholder="Phone" className="border-gray-300 focus:ring-blue-500" />
              <Input placeholder="Message" className="col-span-1 md:col-span-2 border-gray-300 focus:ring-blue-500" />
              <Button className="col-span-1 md:col-span-2 bg-blue-700 hover:bg-blue-800 text-white py-2">Submit</Button>
            </form>
          </div>
        </section>

        <footer className="bg-blue-800 text-white text-center py-6">
          <p>&copy; 2025 TNPSC Academy. All rights reserved.</p>
        </footer>
      </div>
    </div>
  );
}
