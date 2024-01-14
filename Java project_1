import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

class Question {
    private String question;
    private List<String> options;
    private char correctAnswer;

    public Question(String question, List<String> options, char correctAnswer) {
        this.question = question;
        this.options = options;
        this.correctAnswer = correctAnswer;
    }

    public String getQuestion() {
        return question;
    }

    public List<String> getOptions() {
        return options;
    }

    public char getCorrectAnswer() {
        return correctAnswer;
    }
}

class Quiz {
    private List<Question> questions;

    public Quiz(List<Question> questions) {
        this.questions = questions;
    }

    public void start() {
        Scanner scanner = new Scanner(System.in);
        int score = 0;

        for (Question question : questions) {
            System.out.println(question.getQuestion());
            List<String> options = question.getOptions();
            for (int i = 0; i < options.size(); i++) {
                System.out.println((char) ('A' + i) + ". " + options.get(i));
            }

            char userAnswer = getUserAnswer(scanner);

            if (userAnswer == question.getCorrectAnswer()) {
                System.out.println("Correct!\n");
                score++;
            } else {
                System.out.println("Incorrect. The correct answer is " + question.getCorrectAnswer() + ".\n");
            }
        }

        System.out.println("Quiz completed!");
        System.out.println("Your score: " + score + " out of " + questions.size());

        scanner.close();
    }

    private char getUserAnswer(Scanner scanner) {
        char userAnswer;
        do {
            System.out.print("Your answer: ");
            String input = scanner.next().toUpperCase();
            if (input.length() == 1 && input.charAt(0) >= 'A' && input.charAt(0) <= 'Z') {
                userAnswer = input.charAt(0);
                break;
            } else {
                System.out.println("Invalid input. Please enter a valid option (A, B, C, etc.).");
            }
        } while (true);

        return userAnswer;
    }
}

public class Main {
    public static void main(String[] args) {
        List<Question> questions = new ArrayList<>();
        questions.add(new Question("What is the capital of France?", List.of("Paris", "Berlin", "London"), 'A'));
        questions.add(new Question("What is the largest mammal?", List.of("Elephant", "Blue Whale", "Giraffe"), 'B'));
        questions.add(new Question("Which planet is known as the Red Planet?", List.of("Earth", "Mars", "Venus"), 'B'));

        Quiz quiz = new Quiz(questions);
        quiz.start();
    }
}
