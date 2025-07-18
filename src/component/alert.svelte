<script lang="ts">
	type AlertVariant = 'warning' | 'error' | 'success';

	export let variant: AlertVariant = 'warning';
	export let title = '';
	export let message = '';
    
	$: variants = {
		warning: 'text-[10px] bg-yellow-50 text-neutral-950 leading-[14px] font-semibold rounded-[8px]',
		error: 'bg-red-100 text-[14px] text-neutral-950 leading-[14px] font-semibold rounded-[8px]',
		success: 'text-[16px] bg-green-50 text-neutral-950 leading-[14px] font-medium rounded-[8px]'
	} as const;  

	$: icons = {
		warning: '/warning-icon.png',
		error: '/error-icon.png',
		success: '/success-icon.png'
	} as const;
	
	$: styles = variants[variant];
	$: icon = icons[variant]; 
	$: hasTitle = title.length > 0;
	$: hasMessage = message.length > 0;
</script>

<div class="rounded-lg px-2.5 py-2 {styles}">
	<div class="flex {!hasTitle ? 'items-center' : ''} gap-3">
		<div class="flex-shrink-0">
			<img src={icon} alt={variant} />
		</div>
		<div class="flex
		">
			{#if hasTitle}
				<h3 class="text-sm font-medium">{title}</h3>
			{/if}
			{#if hasMessage}
				<div class="{hasTitle ? 'mt-1' : ''} text-sm">
					<slot>{message}</slot>
				</div>
			{/if}
		</div>
	</div>
</div>