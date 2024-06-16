package repository;
import java.util.List;

import org.springframework.data.jpa.repository.JpaRepository;
import org.springframework.stereotype.Repository;
import model.College;

@Repository
public interface CollegeRepository extends JpaRepository<College, Integer> {
    List<College> findAll();
}
