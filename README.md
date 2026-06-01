
<script>
const reveals = document.querySelectorAll('.reveal');
const obs = new IntersectionObserver((entries) => {
  entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); } });
}, { threshold: 0.12 });
reveals.forEach(r => obs.observe(r));

const bars = document.querySelectorAll('.skill-fill');
const barObs = new IntersectionObserver((entries) => {
  entries.forEach(e => { if (e.isIntersecting) { e.target.style.width = e.target.style.width; } });
}, { threshold: 0.3 });
bars.forEach(b => {
  const target = b.style.width;
  b.style.width = '0';
  barObs.observe(b);
  setTimeout(() => { b.style.width = target; }, 300);
});
</script>

</body>
</html>
