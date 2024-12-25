<template>
	<div class="antialiased text-gray-700 bg-gray-100">
		<div class="flex w-full h-screen justify-center items-center" id="app">
			<div class="w-full max-w-xl">
				<h1 class="text-5xl font-bold text-center text-indigo-700">Simple Quiz</h1>
				<div class="bg-white p-12 rounded-lg shadow-lg w-full mt-8">
					<p class="text-2xl font-bold">{{ currentQuestion.question }}</p>
					<div v-for="(answer, key) in currentQuestion.answers" :key="key" class="block mt-4">
						<label
							:for="key"
							class="border border-gray-300 rounded-lg py-2 px-6 text-lg w-full block cursor-pointer">
							<input
								type="radio"
								:id="key"
								:value="key"
								v-model="selectedAnswer"
								class="hidden"
							/>
							{{ answer }}
						</label>
					</div>
					<button
						class="mt-6 bg-indigo-700 text-white py-2 px-4 rounded-lg"
						@click="submitAnswer">
						Submit
					</button>
				</div>
			</div>
		</div>
	</div>
</template>

<script setup>
import { ref, computed } from 'vue';

const questions = ref([
	{
		question: "Rolex is a company that specializes in what type of product?",
		answers: {
			a: 'Bags',
			b: 'Watches',
			c: 'Shoes',
			d: 'Laptops'
		},
		correctAnswer: 'b'
	},
	{
		question: "When did Facebook launch?",
		answers: {
			a: '2005',
			b: '2008',
			c: '2003',
			d: '2004'
		},
		correctAnswer: 'd'
	},
	{
		question: "Albert Einstein had trouble with mathematics when he was in school?",
		answers: {
			a: 'True',
			b: 'False'
		},
		correctAnswer: 'b'
	},
]);

const currentQuestionIndex = ref(0);
const selectedAnswer = ref(null);

const currentQuestion = computed(() => questions.value[currentQuestionIndex.value]);

function submitAnswer() {
	if (selectedAnswer.value === currentQuestion.value.correctAnswer) {
		alert('Correct!');
	} else {
		alert('Wrong!');
	}
	selectedAnswer.value = null;
	if (currentQuestionIndex.value < questions.value.length - 1) {
		currentQuestionIndex.value++;
	} else {
		alert('Quiz finished!');
	}
}
</script>
