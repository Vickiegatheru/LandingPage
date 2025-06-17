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

<!-- Link the external CSS -->
<style>
  @import './app.css';
</style>

<div class="mainLayout">
  <div class="title">
    <div class="column1">
      <div id="widgets">
        <button class="toolbar-button" on:click={handleWidgets} title="Widgets">
          <i class="fas fa-th-large"></i>
        </button>
      </div>
      <div id="lypaAppLink">
        <a href="#">LYPA APP</a>
      </div>
      <div id="web">
        <b>> Web 1920 - 2</b>
      </div>
    </div>
    <div class="column2">
      <div id="zoom">
        <select bind:value={zoom}>
          <option value="0.464">46.4%</option>
          <option value="0.5">50%</option>
          <option value="0.75">75%</option>
          <option value="1">100%</option>
          <option value="1.25">125%</option>
          <option value="1.5">150%</option>
        </select>
      </div>
      <div id="full screen">
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
    <div id="mainImage" style={zoomStyle}>
      <img src="/images/main.png" width="840" height="587" alt="Information" />
    </div>

    <div id="makeComment">
      <div id="commentbox">
        <div id="box1">
          <textarea
            id="commentBox"
            rows="4"
            cols="40"
            placeholder="Make a comment"
            bind:value={commentText}
          ></textarea>
        </div>

        <div id="commentbuttons">
          <button type="button" on:click={handleCancel}>Cancel</button>
          <button type="submit" on:click={() => alert('Thank you for your comment!')}>Submit</button>
        </div>
      </div>

      <div id="box2">
        <p><img src="/images/comment.png" alt="comment" /></p>
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
          <button class="toolbar-button" title="Hide Annotations">
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
