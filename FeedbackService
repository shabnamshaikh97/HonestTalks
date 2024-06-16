package service;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;
import model.Feedback;
import model.College;
import repository.FeedbackRepository;

import java.util.List;

@Service
public class FeedbackService {
    @Autowired
    private FeedbackRepository feedbackRepository;

    public void saveFeedback(Feedback feedback) {
        feedbackRepository.save(feedback);
    }

    public List<Feedback> getFeedbacksByCollege(College college) {
        return feedbackRepository.findByCollege(college);
    }
}
