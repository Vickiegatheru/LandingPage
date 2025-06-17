<script>
  // Handlers from original JS
  function handleWidgets() {
    alert("Widgets clicked!");
  }
  function handleFullscreen() {
    alert("Fullscreen clicked!");
  }
  function handleHelp() {
    alert("Help clicked!");
  }
  function handleCancel() {
    alert("Cancel clicked!");
  }
  function toggleAction() {
    alert("Toggle clicked!");
  }
  function filterAction() {
    alert("Filter clicked!");
  }
  function handleHideAnnotations() {
    alert("Hide Annotations clicked!");
  }
  function handleHome() {
    alert("Home clicked!");
  }
  function handleNavigation() {
    alert("Navigation clicked!");
  }
</script>

<svelte:head>
  <link rel="stylesheet" href="/styles.css">

  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
</svelte:head>


<div class="mainLayout">
  <div class="title">
    <div class="column1">
      <div id="widgets">
        <button class="toolbar-button" on:click={handleWidgets} title="Widgets">
          <i class="fas fa-th-large"></i>
        </button>
      </div>
      <div id="lypaAppLink">
        <a href="">LYPA APP</a>
      </div>
      <div id="web">
        <b>> Web 1920 - 2</b>
      </div>
    </div>

    <div class="column2">
      <div id="zoom">
        <div id="zoom-controls">
          <select id="zoom-select">
            <option value="0.5">50%</option>
            <option value="0.75">75%</option>
            <option value="1">100%</option>
            <option value="1.25">125%</option>
            <option value="1.5">150%</option>
          </select>
        </div>
      </div>
      <div id="fullscreen">
        <button class="toolbar-button" on:click={handleFullscreen} title="Full Screen">
          <i class="fas fa-expand"></i>
        </button>
      </div>
      <div id="help">
        <button class="toolbar-button" on:click={handleHelp} title="Help">
          <i class="fas fa-question-circle"></i>
        </button>
      </div>
      <div id="signin">
        <button>Sign In</button>
      </div>
    </div>
  </div>

  <div class="mainPage">
    <div id="mainImage">
<img src="/images/main.png" width="840" height="587" alt="Information">
    </div>

    <div id="makeComment">
      <div id="commentbox">
        <div id="box1">
          <textarea id="commentBox" name="comment" rows="4" cols="40" placeholder="Make a comment"></textarea>
        </div>
        <div id="commentbuttons">
          <button type="button" on:click={handleCancel}>Cancel</button>
          <button type="submit">Submit</button>
        </div>
      </div>

      <div id="box2">
<p><img src="/images/comment.png" alt="Comment icon" /></p>
        <p>No Comments yet</p>
        <p>Give feedback, ask questions, or start a discussion in the comments.</p>
      </div>

      <div id="commentfooter">
        <div id="part1">
          <button class="icon-button" on:click={toggleAction} title="Toggle">
            <i class="fas fa-toggle-on"></i>
          </button>
          All screen comments
        </div>

        <div id="part2">
          <button class="toolbar-button" on:click={handleHideAnnotations} title="Hide Annotations">
            <i class="fas fa-eye-slash"></i>
          </button>
          <button class="icon-button" on:click={filterAction} title="Filter">
            <i class="fas fa-filter"></i>
          </button>
        </div>
      </div>
    </div>

    <div class="toolbar">
      <button class="toolbar-button" title="Make a Comment">
        <i class="fas fa-comment-alt"></i>
      </button>
      <button class="toolbar-button" title="Navigation">
        <i class="fas fa-code"></i>
      </button>
      <button class="toolbar-button" title="Variables">
        <i class="fas fa-brackets-curly"></i>
      </button>
      <button class="toolbar-button flag" title="Flag">
        <i class="fas fa-flag"></i>
      </button>
    </div>
  </div>

  <div class="footer">
    <div id="adobe">
      <p>Made with Adobe XD</p>
    </div>
    <div id="part3">
      <button class="toolbar-button" on:click={handleHome} title="Home">
        <i class="fas fa-home"></i>
      </button>
    </div>
    <div id="part4">
      <button class="toolbar-button" on:click={handleNavigation} title="Navigation Arrows">
        <i class="fas fa-arrows-alt"></i>
      </button>
    </div>
  </div>
</div>

<style>
body{
  overflow: hidden;
  grid-auto-rows: 1fr 1fr 1fr;
  margin: 0;
  padding: 0;
  height: 100%;
  width: 100%;
  display: flex; /* optional layout */
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.mainLayout{
  grid-row-start: 1;
}

.title{
 display: grid;
grid-template-columns: 4fr 1fr;
border: 1px solid #ccc; /* Thin grey border */
border-radius: 0;        /* Sharp corners */
}

.column1{
columns: auto;
grid-column-start: 1;
width: 875px;
height: 48.67px;

}
#widgets{
  display: inline-block;
}
#web{
  display: inline-block;
}
#lypaAppLink{
  display: inline;
}
.column2 {
  display: flex;            /* Display children in one line */
  flex-direction: row;      /* Default, but explicit */
  align-items: flex-end;
  height: 48.67px;
}


#zoom{
      flex: 1;                         /* Equal width */
      color: white;
      text-align: right;
      line-height: 48.67px;           /* Vertically center text */
      border: none;
      cursor: pointer;

}
#fullscreen{
      flex: 1;                         /* Equal width */
      color: white;
      text-align: right;
      line-height: 48.67px;           /* Vertically center text */
      border: none;
      cursor: pointer;

}
#help{
  flex: 1;                         /* Equal width */
      margin: 0 5px;                   /* Optional spacing */
      color: white;
      text-align: right;
      line-height: 48.67px;           /* Vertically center text */
      border: none;
      cursor: pointer;
      width: 46px;
 

}

#signin{
  flex: 1;                         /* Equal width */
      color: white;
      line-height: 48.67px;           /* Vertically center text */
      border: none;
      cursor: pointer;
      
}
.mainPage {

  display: grid;
  grid-row-start: 2;
  grid-template-columns: 7fr 3fr 0.36fr ;
  height: 450px;
}
#mainImage {
  margin: 30px 0px 0px 0px;
  width: 847x;
  height: 401px;
  overflow: auto;           
  border: 1px solid #ccc;   
}

#mainImage img {
  display: block;           
  max-width: none;          
  max-height: none;
}

#makeComment{
  grid-column-start: 2;
  background-color: #e0e0e0;
  height: 468.5px;
  
}
  button {
    padding: 10px 10px;
    margin: 5px;
    font-size: 16px;
    border: none;
    border-radius: 18px;
    cursor: pointer;
  }
  #commentbuttons{
    display: flex;            
  flex-direction: row;    
    align-items: right;
    display: flex;
      justify-content: flex-end;  }

  button[type="button"] {
  background-color: #e0e0e0;
    color: white;
  }

  button[type="submit"] {
    background-color: #8e938e; 
    color: white;
  }

  button:hover {
    opacity: 0.9;
  }
#commentbox{
  border: 1px solid #ccc; /* Thin grey border */
    border-radius: 0;        /* Sharp corners */
    padding: 10px;
}

.box1{
  display: inline-block;
 }
#commentfooter{  
  display: flex;
  align-items: center;             /* Optional: vertical alignment */
  border: 1px solid #ccc;
  border-radius: 0;
  padding: 10px;
}

#part1{
  justify-content: flex-start;
}
#part2{
display: flex;
  justify-content: flex-end;  /* Align inner items to the right */
  width: 40%; 
}
#box2{
  align-items: center;
}

  .button-group {
    display: flex;
    margin: 20px 0;
  }

  .icon-button {
    background-color: #f0f0f0;
    border: 1px solid #ccc;
    border-radius: 4px; /* You can change to 0 for sharp corners */
    padding: 10px;
    font-size: 18px;
    cursor: pointer;
    transition: background-color 0.2s;
  }

  .icon-button:hover {
    background-color: #e0e0e0;
  }
  
.toolbar {
  grid-column-start: 3;
      display: flex;
      flex-direction: column;
      align-items: right;
      background-color: #fff;
      height: 100vh;
      width: 30px;
    }

    .toolbar-button {
      background: none;
      border: none;
      cursor: pointer;
      font-size: 18px;
      color: #666;
      transition: color 0.2s, background-color 0.2s;
    }

    .toolbar-button:hover {
      color: #000;
    }

    .toolbar-button.flag {
      transform: rotate(-45deg);
      font-size: 18px;
      color: #bbb;
      align-items: right;
    }

.footer{
grid-row-start: 3;
display: flex;            /* Display children in one line */
  flex-direction: row;
}

#adobe{
  position: absolute;
  
  
  margin-left: -45%; 

}
#part3{
position: absolute;
margin-left: -15% ;
}

#part4{ 
position: relative;
  margin-left: -10%; 
}

.icon-button1 {
display: inline-block;
  bottom: 80px;
  right: 100px;
  background: blue;
  border: none;
  cursor: pointer;
  color: #666;
  font-size: 16px;
}

.icon-button1:hover {
  color: #000;
}
@media (max-width: 768px) {
  .mainPage {
    grid-template-columns: 1fr;
  }

  .column1,
  .column2 {
    flex-direction: column;
    gap: 10px;
    align-items: flex-start;
  }

  #makeComment {
    width: 100%;
    height: auto;
  }

  .toolbar {
    flex-direction: row;
    justify-content: space-around;
    width: 100%;
    height: auto;
    padding: 10px 0;
  }

  .title {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  #mainImage img {
    max-width: 100%;
    height: auto;
  }

  select,
  button {
    width: 100%;
    max-width: 100%;
  }
}


</style>
