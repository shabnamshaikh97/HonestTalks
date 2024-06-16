package model;


import jakarta.persistence.Entity;
import jakarta.persistence.GeneratedValue;
import jakarta.persistence.GenerationType;
import jakarta.persistence.Id;

@Entity
public class User {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private int id;
    
    private String anonymousName;

  
    public User() {
    }

    public User(String anonymousName) {
        this.anonymousName = anonymousName;
    }

    
    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public String getAnonymousName() {
        return anonymousName;
    }

    public void setAnonymousName(String anonymousName) {
        this.anonymousName = anonymousName;
    }
}
