<template>
<link
  rel="stylesheet"
  href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css"/>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">

  <section class="hero">
    <div class="image"><img src="/images/bg-schedule.jpg" alt=""></div>


    <div class="content">
      <span class="title">Craft beer</span>
      <h2>Event Schedule</h2>
      <p>Join us for unforgettable beer experiences, brewery tours, tasting sessions, seasonal celebrations, and community gatherings. Whether you're a craft beer enthusiast or just beginning your journey, our events offer the perfect opportunity to explore unique flavors, meet fellow beer lovers, and create memorable moments.</p>
    </div>
  </section>

    <section class="schedule-section">
    <div class="container">


      <div class="schedule-list">
        <EventScheduleItem
          icon="fa-regular fa-clock"
          title="Event Begins"
          time="2:00 PM"
        />

        <EventScheduleItem
          icon="fa-solid fa-users"
          title="Introduction by the MC"
          time="3:15 PM"
        />

        <EventScheduleItem
          icon="fa-solid fa-music"
          title="DJ Wha-Wah"
          time="3:30 PM"
        />

             <EventScheduleItem
          icon="fa-solid fa-award"
          title="Blind tasting live session"
          time="6:40 PM"
        />

             <EventScheduleItem
          icon="fa-solid fa-award"
          title="Start award ceremony"
          time="7:30 PM"
        />

          <EventScheduleItem
          icon="fa-solid fa-music"
          title="Live music by The Broken Cymbal"
          time="8:30 PM"
        />

             <EventScheduleItem
          icon="fa-solid fa-business-time"
          title="Event Ends"
          time="11:30 PM"
        />


      </div>
      
    </div>
  </section>


</template>


<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap');

html, body {
  font-family: 'Inter', sans-serif;
}




* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Inter', sans-serif;
  
}

.hero {
  display: flex;
  align-items: center;
  gap: 60px;
  max-width: 1200px;
  margin: 100px auto;
  padding: 0 20px;
  align-items: center;
  
}

.image{
  flex: 1;
}

.image img{
  width: 100%;
  border-radius: 20px;
  display: block;
  box-shadow: 0 10px 30px rgba(0,0,0,0.2);
}

.content {
  flex: 1;
}

.title {
  color: #d4a017;
  font-weight: 600;
  letter-spacing: 2px;
}

.content h2 {

  font-size: 2rem;
  color: #222;

    font-size: 3rem;
    margin: 15px 0;
    color: #222;

}

.content p{
  color: #666;
  line-height: 1.8;
  margin-bottom: 30px;
}

.container {
   width: 100%;
   max-width: 1200px;
    margin: 0 auto;
    padding: 0 1.5rem;
    display: block;
}


.schedule-list {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}


@media (max-width: 768px ) {
  .hero {
    flex-direction: column;
    text-align: center;
    gap: 30px;
    margin: auto 50px;
  }
}
  @media (max-width: 480px) {
  .hero {
    padding: 0 15px;
    margin: 30px auto;
  }

  .image img {
    border-radius: 15px;
  }

  .content h2 {
    font-size: 1.7rem;
  }

  .content p {
    font-size: 0.9rem;
  }

  .schedule-list {
    gap: 1rem;
  }
}
</style>