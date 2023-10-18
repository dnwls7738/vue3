<template>
	<div className="youtube__search container">
		<form @submit.prevent="SearchYoutube()">
			<div>
				<label for="search" class="sr-only">검색하기</label>
				<input
					v-model="search"
					type="search"
					id="search"
					placeholder="검색어를 입력하세요"
				/>
				<button type="submit" value="search">검색</button>
			</div>
		</form>

		<div className="youtube__list">
			<ul>
				<li v-for="youtube in youtubes" :key="youtube.id.videoId">
					<a href="">
						<img
							:src="youtube.snippet.thumbnails.medium.url"
							alt="movie.snippet.title"
						/>
						<p>
							{{ youtube.snippet.title }}
						</p>
					</a>
				</li>
			</ul>
		</div>
	</div>
</template>
<script>
export default {};
</script>
<style></style>
