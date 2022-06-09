<script lang="ts">
	import { COLS, ROWS } from "../../utils";

	import { Tile } from "../board";
	export let visible: boolean;
</script>

<h3>how to play</h3>
<div>Guess the <strong>ZOODLE</strong> in {ROWS} tries.</div>
<div>Each guess must be a valid animal-themed word. Hit the enter button to submit.</div>
<div>
	After each guess, the color of the tiles will change to show how close your guess was to the
	word.
</div>
<div class:complete={visible} class="examples">
	<div><strong>Examples</strong></div>
	<div class="row">
		<Tile value="r" state="🟩" />
		<Tile value="a" state="⬜" />
		<Tile value="v" state="⬜" />
		<Tile value="e" state="⬜" />
		<Tile value="n" state="⬜" />
	</div>
	<div>The letter <strong>R</strong> is in the word and in the correct spot.</div>
	<div class="row">
		<Tile value="q" state="⬜" />
		<Tile value="u" state="⬜" />
		<Tile value="a" state="⬜" />
		<Tile value="c" state="⬜" />
		<Tile value="k" state="🟨" />
	</div>
	<div>The letter <strong>K</strong> is in the word but in the wrong spot.</div>
	<div class="row">
		<Tile value="s" state="⬜" />
		<Tile value="h" state="⬜" />
		<Tile value="e" state="⬛" />
		<Tile value="l" state="⬜" />
		<Tile value="l" state="⬜" />
	</div>
	<div>The letter <strong>E</strong> is not in the word in any spot.</div>
</div>
<div>
	This is a recreation of the original <a
		href="https://www.nytimes.com/games/wordle/"
		target="_blank">Wordle</a
	>
	by Josh Wardle with additional modes and features, allowing you to play infinite wordles. Switch
	to infinite mode to play an unlimited number of times.
	<br /><br />
	Open the settings menu to see some of the additional features.
	<br /><br />
	Zoodle is based on <a href="https://mikhad.github.io/wordle/" target="_blank">Wordle+</a> by <a href="https://github.com/MikhaD" target="_blank">MikhaD</a>.
</div>

<style lang="scss">
	div {
		margin: 14px 0;
	}
	.examples {
		border-top: 1px solid var(--border-primary);
		border-bottom: 1px solid var(--border-primary);
		:global(.row > *) {
			height: 100%;
			aspect-ratio: 1;
		}
		&:not(.complete) :global(.row .back) {
			transition-delay: 0.3s;
		}
	}
	.row {
		height: 40px;
		display: flex;
		gap: 4px;
	}
</style>
