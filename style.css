const music = document.querySelector("audio");
const img = document.querySelector("img");
const play = document.getElementById("play");

const artist = document.getElementById("artist");
const title = document.getElementById("title");
const prev = document.getElementById("prev");
const next = document.getElementById("next");

let progress = document.getElementById("progress");
let total_duration = document.getElementById("duration");
let current_time = document.getElementById("current_time");

const progress_div = document.getElementById("progress_div");

const icon = document.getElementById("icon");

const songs = [{
    name: "music-1",
    title: "faded",
    artist: "alan walker",
    pic: "pic-1",
  },
  {
    name: "music-2",
    title: "mi gente",
    artist: "willy william",
    pic: "pic-2",
  },
  {
    name: "music-3",
    title: "Ram Siya Ram",
    artist: "Sachet Tandon",
    pic: "pic-3",
  },
  {
    name: "music-4",
    title: "Shiva Tandava",
    artist: "Uma Mohan",
    pic: "pic-4",
  },
  {
    name: "music-5",
    title: "zindagi",
    artist: "Zubin Nautiyal",
    pic: "pic-5",
  },
  {
    name: "music-6",
    title: "Tu Jo Mila",
    artist: "KK, Pritam",
    pic: "pic-6",
  },
];
var isplaying = false;

const playMusic = function() {
  isplaying = true;
  music.play();
  play.classList.replace("fa-play", "fa-pause");
  img.classList.add("anime");
};
// for pause function
const pauseMusic = function() {
  isplaying = false;
  music.pause();
  play.classList.replace("fa-pause", "fa-play");
  img.classList.remove("anime");
};
play.addEventListener("click", function() {
  isplaying ? pauseMusic() : playMusic();
});


// changing music data
const loadSong = function(songs) {
  title.textContent = songs.title;
  artist.textContent = songs.artist;
  music.src = "music/" + songs.name + ".mp3";
  img.src = "images/" + songs.pic + ".jpg";
};

var songIndex = 0;
const nextSong = function() {
  songIndex = (songIndex + 1) % songs.length;
  loadSong(songs[songIndex]);
  playMusic();
}
const prevSong = function() {
  songIndex = (songIndex - 1 + songs.length) % songs.length;
  loadSong(songs[songIndex]);
  playMusic();
}

//  progress bar

music.addEventListener("timeupdate", function(event) {
  const {
    currentTime,
    duration
  } = event.srcElement;
  let progress_time = (currentTime / duration) * 100;
  progress.style.width = `${progress_time}%`;

  // music duration update
  let min_duration = Math.floor(duration / 60);
  let sec_duration = Math.floor(duration % 60);

  if (sec_duration < 10)
    sec_duration = `0${sec_duration}`;
  let tot_duration = `${min_duration}:${sec_duration}`;
  if (duration) {
    total_duration.textContent = `${tot_duration}`;
  }

  // current duration update
  let min_currentTime = Math.floor(currentTime / 60);
  let sec_currentTime = Math.floor(currentTime % 60);
  if (sec_currentTime < 10)
    sec_currentTime = `0${sec_currentTime}`;
  let tot_currentTime = `${min_currentTime}:${sec_currentTime}`;
  if (currentTime) {
    current_time.textContent = `${tot_currentTime}`;
  }
});

progress_div.addEventListener("click", function(event) {
  const {
    duration
  } = music; // duration=music.duration;
  let move_progress = (event.offsetX / event.srcElement.clientWidth) * duration;
  music.currentTime = move_progress;
});
// next song if music ended
music.addEventListener("ended", nextSong);

next.addEventListener("click", nextSong);
prev.addEventListener("click", prevSong);


// mode

icon.addEventListener("click", function() {
  document.body.classList.toggle("dark-theme");
  if (document.body.classList.contains("dark-theme")) {
    icon.classList.replace("fa-moon", "fa-sun");
  } else {
    icon.classList.replace("fa-sun", "fa-moon");
  }
});
