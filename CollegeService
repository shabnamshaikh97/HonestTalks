package service;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;
import model.College;
import repository.CollegeRepository;
import repository.FeedbackRepository;
import model.Feedback;

import java.util.List;

@Service
public class CollegeService {

    @Autowired
    private CollegeRepository collegeRepository;

    @Autowired
    private FeedbackRepository feedbackRepository;

   
    public CollegeService() {
        super();  
    }

    public List<College> getAllColleges() {
        return collegeRepository.findAll();
    }

    public College getCollegeById(int id) {
        return collegeRepository.findById(id).orElse(null);
    }

    public void saveCollege(College college) {
        collegeRepository.save(college);
    }

    public void updateCollege(College college) {
        List<Feedback> feedbacks = feedbackRepository.findByCollege(college);
        if (feedbacks != null && !feedbacks.isEmpty()) {
            double averageRating = feedbacks.stream()
                                            .mapToInt(Feedback::getRating)
                                            .average()
                                            .orElse(0.0);
            college.setRating(averageRating);
        } else {
            college.setRating(0);
        }
        collegeRepository.save(college);
    }
