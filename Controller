package controller;
import org.springframework.ui.Model;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.RequestParam;
import model.College;
import service.CollegeService;
import org.springframework.stereotype.Controller;
import java.util.List;
import model.Feedback;
import service.FeedbackService;
@Controller
public class HonestTalkController {

    @Autowired
    private CollegeService collegeService;

    @Autowired
    private FeedbackService feedbackService;

    @GetMapping("/")
    public String index() {
        return "index";
    }

    @GetMapping("/college")
    public String viewCollege(@RequestParam("collegeId") int collegeId, Model model) {
        College college = collegeService.getCollegeById(collegeId);
        List<Feedback> feedbacks = feedbackService.getFeedbacksByCollege(college);
        model.addAttribute("college", college);
        model.addAttribute("feedbacks", feedbacks);
        return "college";
    }

    @PostMapping("/submitFeedback")
    public String saveFeedback(@RequestParam("collegeId") int collegeId,
                               @RequestParam("anonymousName") String anonymousName,
                               @RequestParam("feedback") String feedback,
                               @RequestParam("rating") int rating) {
        College college = collegeService.getCollegeById(collegeId);
        Feedback feedbackEntity = new Feedback();
        feedbackEntity.setCollege(college);
        feedbackEntity.setAnonymousName(anonymousName);
        feedbackEntity.setFeedback(feedback);
        feedbackEntity.setRating(rating);
        feedbackService.saveFeedback(feedbackEntity);
        collegeService.updateCollege(college);
        return "redirect:/feedbacks?collegeId=" + collegeId;
    }

    @GetMapping("/feedbacks")
    public String viewFeedbacks(@RequestParam("collegeId") int collegeId, Model model) {
        College college = collegeService.getCollegeById(collegeId);
        List<Feedback> feedbacks = feedbackService.getFeedbacksByCollege(college);
        model.addAttribute("college", college);
        model.addAttribute("feedbacks", feedbacks);
        return "feedback";
    }

    @GetMapping("/honesttalk")
    public String viewAverageRatings(Model model) {
        List<College> colleges = collegeService.getAllColleges();
        model.addAttribute("colleges", colleges);
        return "honesttalk";
    }
}
