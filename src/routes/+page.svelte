<script>
    import { PowerTable } from '@muonw/powertable';
    import ptData from '$lib/data.json';
    import { Button, MenuItem, ResponsiveMenu, Toggle } from 'svelte-ux';
    
    const ptOptions = {
	rowsPerPage: 100,
	rowsPerPageOptions: [10, 100, 200, 1000],
	footerText: false,
	footerFilters: false,
};
    </script>
        <Toggle let:on={open} let:toggle let:toggleOff>
            <Button on:click={toggle}>
              Click me
              <ResponsiveMenu {open} on:close={toggleOff}>
                <MenuItem on:click={toggleOff}>Refresh</MenuItem>
                <MenuItem on:click={toggleOff}>Settings</MenuItem>
                <MenuItem on:click={toggleOff}>Help</MenuItem>
                <MenuItem on:click={toggleOff}>Sign In</MenuItem>
                <MenuItem on:click={toggleOff} disabled>Disabled</MenuItem>
              </ResponsiveMenu>
            </Button>
          </Toggle>


    <PowerTable {ptData} {ptOptions} />