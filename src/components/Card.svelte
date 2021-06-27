<script lang="ts">
	import { maxCardWidth } from '../constants';
	import { spaceJoin } from '../utils';

	export let suite: CardSuite = 'hearts';
	export let value: CardValue = 'A';
	let classStr = '';
	export { classStr as class };
	let cardJpgPath: string;
	$: {
		const jpgFolder = `/images/cards-jpg`;
		cardJpgPath = `${jpgFolder}/${value}${suite
			.charAt(0)
			.toUpperCase()}.jpg`;
	}
</script>

<div class={spaceJoin(['card', classStr])}>
	<img
		src={cardJpgPath}
		alt={`${value} of ${suite} card.`}
		style="max-width:{maxCardWidth}px; height: auto;" />
</div>
