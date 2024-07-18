# 😄About me

```PersonalIntroduction.java
public class PersonalIntroduction {

    public static void main(String[] args) {
        var person = Person.createPerson();
        System.out.println(person);
    }
}

class Person {
    private final String name;
    private final Hobby[] hobbies;
    private final WorkExperience[] workExperiences;

    private Person(String name, Hobby[] hobbies, WorkExperience[] workExperiences) {
        this.name = name;
        this.hobbies = hobbies;
        this.workExperiences = workExperiences;
    }

    public static Person createPerson() {
        var hobbies = new Hobby[] {
            new Hobby("Home Gardening"),
            new Hobby("Motorcycling"),
            new Hobby("Drones")
        };
        var workExperiences = new WorkExperience[] {
            new WorkExperience("SES Company", 6),
            new WorkExperience("E-Commerce", 7),
            new WorkExperience("Fintech", 0)
        };
        return new Person("John Doe", hobbies, workExperiences);
    }

    @Override
    public String toString() {
        var sb = new StringBuilder();
        sb.append("Name: ").append(name).append("\n")
          .append("Hobbies:\n");
        for (var hobby : hobbies) {
            sb.append("- ").append(hobby).append("\n");
        }
        sb.append("Work Experience:\n");
        for (var experience : workExperiences) {
            sb.append("- ").append(experience).append("\n");
        }
        return sb.toString();
    }
}

record Hobby(String name) {}

record WorkExperience(String type, int years) {
    @Override
    public String toString() {
        return type + " (" + years + " years)";
    }
}

```
