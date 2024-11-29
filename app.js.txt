// app.js
document.addEventListener("DOMContentLoaded", () => {
    const pages = document.querySelectorAll(".page");
    const menuBar = document.getElementById("menu-bar");

    const showPage = (id) => {
        pages.forEach((page) => page.classList.remove("active"));
        document.getElementById(id).classList.add("active");
    };

    // Initial Landing Page
    setTimeout(() => showPage("login-page"), 3000);

    // Event Listeners
    document.getElementById("sign-up").addEventListener("click", () => showPage("signup-page"));
    document.getElementById("login-redirect").addEventListener("click", () => showPage("login-page"));
    document.getElementById("explore-retreats").addEventListener("click", () => showPage("booking-page"));

    // Menu Bar Toggle
    document.getElementById("menu-button").addEventListener("click", () => {
        menuBar.classList.toggle("hidden");
    });

    // Mock Payment Page
    document.getElementById("booking-form").addEventListener("submit", (e) => {
        e.preventDefault();
        showPage("payment-page");
    });

    document.getElementById("payment-form").addEventListener("submit", (e) => {
        e.preventDefault();
        alert("Payment Successful! See you soon at WellnessLoka.");
        showPage("home-page");
    });
});
