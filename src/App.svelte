<script>
  let zoom = "0.464";
  let commentText = "";

  function handleCancel() {
    commentText = "";
    alert("Cancel clicked!");
  }

  function handleWidgets() {
    alert("Widgets clicked!");
  }

  function handleFullscreen() {
    alert("Fullscreen clicked!");
  }

  function handleHelp() {
    alert("Help clicked!");
  }

  function toggleAction() {
    alert("Toggle clicked!");
  }

  function filterAction() {
    alert("Filter clicked!");
  }

  function handleHome() {
    alert("Home clicked!");
  }

  function handleNavigation() {
    alert("Navigation clicked!");
  }

  $: zoomStyle = `transform: scale(${zoom})`;
</script>

<style>
  body {
    margin: 0;
    padding: 0;
    overflow: hidden;
    font-family: sans-serif;
  }

  .mainLayout {
    display: flex;
    flex-direction: column;
    height: 100vh;
  }

  .title {
    display: grid;
    grid-template-columns: 4fr 1fr;
    padding: 10px;
    border: 1px solid #ccc;
  }

  .column1 {
    display: flex;
    align-items: center;
    gap: 20px;
  }

  .column2 {
    display: flex;
    justify-content: space-around;
    align-items: center;
  }

  .mainPage {
    display: grid;
    grid-template-columns: 7fr 3fr 0.36fr;
    flex: 1;
  }

  #mainImage {
    border: 1px solid #ccc;
    overflow: auto;
    padding: 10px;
  }

  #makeComment {
    background-color: #e0e0e0;
    padding: 10px;
  }

  textarea {
    width: 100%;
    padding: 8px;
    resize: vertical;
  }

  #commentbuttons {
    display: flex;
    justify-content: flex-end;
    gap: 10px;
    margin-top: 10px;
  }

  #commentfooter {
    display: flex;
    justify-content: space-between;
    margin-top: 20px;
    padding: 10px;
    border: 1px solid #ccc;
  }

  .toolbar {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 10px;
    gap: 10px;
    background: #fff;
  }

  .toolbar-button {
    background: none;
    border: none;
    cursor: pointer;
    font-size: 18px;
    color: #666;
  }

  .toolbar-button:hover {
    color: #000;
  }

  .toolbar-button.flag {
    transform: rotate(-45deg);
  }

  .footer {
    display: flex;
    justify-content: space-between;
    padding: 10px;
  }
</style>

<div class="mainLayout">
  <div class="title">
    <div class="column1">
      <button class="toolbar-button" on:click={handleWidgets} title="Widgets">
        <i class="fas fa-th-large"></i>
      </button>
      <a href="#">LYPA APP</a>
      <b>> Web 1920 - 2</b>
    </div>
    <div class="column2">
      <select bind:value={zoom}>
        <option value="0.464">46.4%</option>
        <option value="0.5">50%</option>
        <option value="0.75">75%</option>
        <option value="1">100%</option>
        <option value="1.25">125%</option>
        <option value="1.5">150%</option>
      </select>

      <button class="toolbar-button" on:click={handleFullscreen} title="Full Screen">
        <i class="fas fa-expand"></i>
      </button>
      <button class="toolbar-button" on:click={handleHelp} title="Help">
        <i class="fas fa-question-circle"></i>
      </button>
      <button class="toolbar-button">Sign In</button>
    </div>
  </div>

  <div class="mainPage">
    <div id="mainImage" style={zoomStyle}>
      <img src="/images/main.png" alt="Main visual" width="840" height="587" />
    </div>

    <div id="makeComment">
      <textarea bind:value={commentText} placeholder="Make a comment"></textarea>

      <div id="commentbuttons">
        <button type="button" on:click={handleCancel}>Cancel</button>
        <button type="submit" on:click={() => alert('Thank you for your comment!')}>Submit</button>
      </div>

      <div id="box2" style="margin-top: 20px;">
        <p><img src="/images/comment.png" alt="No comments" /></p>
        <p>No Comments yet</p>
        <p>Give feedback, ask questions, or start a discussion in the comments.</p>
      </div>

      <div id="commentfooter">
        <div>
          <button class="toolbar-button" on:click={toggleAction}>
            <i class="fas fa-toggle-on"></i>
          </button>
          All screen comments
        </div>
        <div>
          <button class="toolbar-button" title="Hide Annotations">
            <i class="fas fa-eye-slash"></i>
          </button>
          <button class="toolbar-button" on:click={filterAction} title="Filter">
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
    <div><p>Made with Adobe XD</p></div>
    <div>
      <button class="toolbar-button" on:click={handleHome}>
        <i class="fas fa-home"></i>
      </button>
    </div>
    <div>
      <button class="toolbar-button" on:click={handleNavigation}>
        <i class="fas fa-arrows-alt"></i>
      </button>
    </div>
  </div>
</div>
