package util;

import java.security.SecureRandom;
import java.util.UUID;

public class AnonymousNameGenerator {

    
    private static final SecureRandom secureRandom = new SecureRandom();

    // anonymous names
    private static final String[] adjectives = {
        "Brave", "Calm", "Eager", "Fancy", "Gentle", "Happy", "Jolly", "Kind", "Lively", "Merry", "Nice", "Proud", "Silly", "Witty", "Zealous"
    };

    private static final String[] nouns = {
        "Lion", "Tiger", "Bear", "Wolf", "Fox", "Hawk", "Eagle", "Shark", "Whale", "Penguin", "Dolphin", "Dragon", "Phoenix", "Unicorn", "Griffin"
    };

    public static String generateAnonymousName() {
        // Generating anonymous name by combining an adjective and a noun
        String adjective = adjectives[secureRandom.nextInt(adjectives.length)];
        String noun = nouns[secureRandom.nextInt(nouns.length)];
        int randomNum = secureRandom.nextInt(100); // Adding a number to ensure uniqueness

        return adjective + noun + randomNum;
    }

    public static String generateUUIDAnonymousName() {
        // Generating a unique anonymous name using UUID and substring it to get 8 characters
        return UUID.randomUUID().toString().substring(0, 8);
    }
}
