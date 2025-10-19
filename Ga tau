const btnMau = document.getElementById('btnMau');
const btnTidakMau = document.getElementById('btnTidakMau');
const motifCanvas = document.getElementById('motif');

function showMotif(type) {
  motifCanvas.classList.remove('hide');
  motifCanvas.width = window.innerWidth;
  motifCanvas.height = window.innerHeight;
  const ctx = motifCanvas.getContext('2d');
  let hearts = [];
  for (let i = 0; i < 50; i++) {
    hearts.push({
      x: Math.random() * motifCanvas.width,
      y: -30,
      size: 18 + Math.random()*12,
      speed: 2 + Math.random()*2,
      color: type === 'mau' ? '#ff5a5f' : '#444'
    });
  }
  function drawHeart(x, y, size, color) {
    ctx.save();
    ctx.translate(x, y);
    ctx.scale(size/35, size/35);
    ctx.beginPath();
    ctx.moveTo(0, 0);
    ctx.bezierCurveTo(0, -14, -17, -14, -17, 0);
    ctx.bezierCurveTo(-17, 12, 0, 19, 0, 35);
    ctx.bezierCurveTo(0, 19, 17, 12, 17, 0);
    ctx.bezierCurveTo(17, -14, 0, -14, 0, 0);
    ctx.closePath();
    ctx.fillStyle = color;
    ctx.fill();
    ctx.restore();
  }
  let frame = 0;
  function animate() {
    ctx.clearRect(0, 0, motifCanvas.width, motifCanvas.height);
    for (let h of hearts) {
      drawHeart(h.x, h.y, h.size, h.color);
      h.y += h.speed;
      if (h.y > motifCanvas.height + 35) h.y = -30;
    }
    frame++;
    if (frame < 140) requestAnimationFrame(animate);
    else motifCanvas.classList.add('hide');
  }
  animate();
}

btnMau.addEventListener('click', () => {
  showMotif('mau');
  alert('Terima kasih sudah memilih \"Mau\"! ❤️');
});

btnTidakMau.addEventListener('click', () => {
  showMotif('tidak');
  alert('Yah, kamu memilih \"Tidak Mau\". 💔');
});
