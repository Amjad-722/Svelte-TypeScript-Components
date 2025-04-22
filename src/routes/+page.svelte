<script>
	import Alert from "../component/alert.svelte";
	import Badge from "../component/badge.svelte";
	import EachLoop from "../component/each-loop.svelte";




</script>
<section class="h-dvh mx-auto items-center justify-center flex flex-col">

<div class="flex-flex-col gap-5">

	<Alert variant="warning" title="Warning" 
  message="Please check your settings. Some required fields are missing or incorrectly formatted." />
<hr class="p-2">
<Alert variant="success" title="Success" 
  message="Your changes have been saved successfully. The system is now up to date." />
<hr class="p-2">
<Alert variant="error" title="Error" 
  message="An unexpected error occurred. Please try again or contact support if the issue persists." />
</div>
    <div class="mt-23"></div>
    <Badge />
    <Badge size="sm" status="success" >wekjkr</Badge>
    <Badge size="md" status="warning" >wekjkr</Badge>
    <Badge size="lg" status="default" beforeIcon="" >wekjkr</Badge>
    <div class="mt-23"></div>
 <EachLoop />

</section>
