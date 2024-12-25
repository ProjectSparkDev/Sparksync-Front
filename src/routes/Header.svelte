<script lang="ts">
	import {
		Collapse,
		Nav,
		NavItem,
		NavbarToggler,
		NavLink,
		Navbar,
		NavbarBrand,
		Image
	} from '@sveltestrap/sveltestrap';

    let isOpen = true;

    function handleUpdate(event: any) {
        isOpen = event.detail.isOpen;
    }
</script>

<Navbar color="dark" theme="dark" expand="md" container="md">
	<NavbarBrand href="/" class="me-auto">
		<Image src="img/LogoOutline.png" height="25" loading="lazy" alt="Spark Logo" />
	</NavbarBrand>
	<NavbarToggler on:click={() => (isOpen = !isOpen)} />
	<Collapse {isOpen} navbar expand="md" on:update={handleUpdate}>
		<Nav navbar>
			<NavItem>
				<NavLink href="/">Home</NavLink>
			</NavItem>
			<NavItem>
				<NavLink href="/faq">FAQ</NavLink>
			</NavItem>
			<NavItem>
				<NavLink href="/help">Help</NavLink>
			</NavItem>
            <NavItem>
                <NavLink href="/login">Login</NavLink>
            </NavItem>
		</Nav>
	</Collapse>
</Navbar>
