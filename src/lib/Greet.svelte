<script>
  import { invoke } from "@tauri-apps/api/tauri";

  let name = "";
  let greetMsg = "";
  let appLocation = "";

  // async function greet() {
  //   // Learn more about Tauri commands at https://tauri.app/v1/guides/features/command
  //   greetMsg = await invoke("greet", { name });
  //   // invoke("launch_app");
  // }

  async function launch() {
    console.log(appLocation);
    invoke("launch_app", { appLocation });
  }
</script>

<div>
  <form class="row" on:submit|preventDefault={launch}>
    <!-- <input id="greet-input" placeholder="Enter a name..." bind:value={name} /> -->
    <input
      id="greet-input"
      placeholder="Enter an app directory..."
      bind:value={appLocation}
    />
    <button type="submit">Launch!</button>
    <p>{appLocation}</p>
  </form>
</div>
