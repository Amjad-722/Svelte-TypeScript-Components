<script lang="ts">
	import { createEventDispatcher } from 'svelte';

	const dispatch = createEventDispatcher();

	export let size = '';
	export let className = '';
	export let beforeIcon = '';
    export let afterIcon = '';
	export let status = '';
	export let variant = '';

	let visible = true;

	$: sizeClass = {
		sm: 'px-1 py-1 text-[10px] leading-[14px] font-semibold rounded-[8px]',
		md: 'px-2 py-2 text-[14px] leading-[14px] font-semibold rounded-[8px]',
		lg: 'px-2 py-2 text-[16px] leading-[14px] font-medium rounded-[8px]',
		full: 'w-full py-2.5 text-lg'
	}[size];

	$: statusStyle = {
		default: 'border border-neutral-200 bg-neutral',
		success: 'bg-green-200 text-[#1FC16B] hover:bg-primary-600',
		warning: 'bg-red-100 text-red hover:bg-success-600',
		outline: 'border border-neutral-200 bg-white text-neutral-600 hover:bg-neutral-50',
		
	};

	$: className = status
		? statusStyle[status as keyof typeof statusStyle] || ``
		: ``;
</script>

{#if visible}
	<!-- svelte-ignore a11y-click-events-have-key-events -->
	<!-- svelte-ignore a11y-no-static-element-interactions -->
	<div
		class={` cursor-pointer gap-1 inline-flex items-center ${sizeClass} ${className} ${
			variant === 'outline' ? 'border' : ''
		} `}
		on:click={(event) => dispatch('click', event)}
	>
		{#if beforeIcon}
			<img src={beforeIcon} alt="Badge Icon" class="h-5 w-5" />
		{/if}
		<slot />
        {#if afterIcon}
			<img src={afterIcon} alt="Badge Icon" class="h-5 w-5" />
		{/if}
	</div>
{/if}