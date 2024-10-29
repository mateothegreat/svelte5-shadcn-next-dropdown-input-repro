<script lang="ts">
  import { buttonVariants } from "$lib/components/ui/button/";
  import * as DropdownMenu from "$lib/components/ui/dropdown-menu";
  import { Input } from "$lib/components/ui/input";
</script>

<div class="flex h-screen flex-col items-center justify-center gap-5">
  <div class="text-sm text-pink-500">When using the dropdown menu, focus hijacking can occur when the menu is open and the user starts typing in the input field.</div>
  <div class="text-sm text-gray-500">
    <ul>
      <li>1. To reproduce focus hijacking, open the dropdown menu and start typing in the input field.</li>
      <li>2. Re-focus the textbox to regain focus.</li>
    </ul>
  </div>
  <DropdownMenu.Root>
    <DropdownMenu.Trigger class={buttonVariants({ variant: "outline" })}>Open</DropdownMenu.Trigger>
    <DropdownMenu.Content class="w-56">
      <DropdownMenu.Group>
        <DropdownMenu.GroupHeading>My Account</DropdownMenu.GroupHeading>
        <DropdownMenu.Separator />
        <DropdownMenu.Group>
          <DropdownMenu.Item
            onclick={(e) => {
              // Prevent menu from closing:
              e.preventDefault();
            }}>
            <Input placeholder="start typing.." />
          </DropdownMenu.Item>
        </DropdownMenu.Group>
        <DropdownMenu.Group>
          <DropdownMenu.Item>a</DropdownMenu.Item>
          <DropdownMenu.Item>b</DropdownMenu.Item>
          <DropdownMenu.Item>c</DropdownMenu.Item>
        </DropdownMenu.Group>
      </DropdownMenu.Group>
    </DropdownMenu.Content>
  </DropdownMenu.Root>
</div>
