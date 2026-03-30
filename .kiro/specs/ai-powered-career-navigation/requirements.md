# Requirements Document

## Introduction

The SKLG Career Navigator is an AI-powered platform designed to guide high school students, undergraduate aspirants, career switchers, and educational institutions through personalized career planning. The system leverages Generative AI and graph-based intelligence to analyze student profiles, recommend optimal career paths, generate structured roadmaps, suggest best-fit colleges, and continuously monitor progress with dynamic re-routing capabilities—similar to how Google Maps recalculates routes when users deviate from the planned path.

## Glossary

- **System**: The SKLG Career Navigator platform
- **Stude
 journeys with nodes (milestones) and edges (transitions)
- **AI_Engine**: Generative AI models that analyze profiles and generate recommendations
- **College_Matcher**: Component that recommends colleges aligned with career goals
- **Progress_Monitor**: Component that tracks student advancement and triggers re-routing
- **Deviation**: When a student's actual progress differs from the planned route
- **Re-routing**: Dynamic recalculation of the path to the career destination when deviation occurs
- **Institution**: Educational organization using the platform to guide multiple students

## Requirements

### Requirement 1: Student Profile Management

**User Story:** As a student, I want to create and maintain a comprehensive profile, so that the system can provide personalized career recommendations.

#### Acceptance Criteria

1. WHEN a student creates a profile, THE System SHALL collect name, age, current education level, interests, career goals, hobbies, and location
2. WHEN a student updates their profile, THE System SHALL persist the changes and trigger re-analysis of recommendations
3. WHEN a student provides aptitude test scores, THE System SHALL store them and incorporate them into career analysis
4. WHEN a student adds academic records, THE System SHALL validate the format and store transcripts, grades, and achievements
5. THE System SHALL support profile data in structured JSON format for AI processing
6. WHEN profile data is incomplete, THE System SHALL identify missing required fields and prompt the student

### Requirement 2: AI-Powered Career Recommendation

**User Story:** As a student, I want AI-driven career recommendations based on my profile, so that I can discover the most suitable career paths.

#### Acceptance Criteria

1. WHEN a student completes their profile, THE AI_Engine SHALL analyze interests, skills, aptitude scores, and goals to generate career recommendations
2. WHEN generating recommendations, THE AI_Engine SHALL rank careers by suitability score
3. WHEN presenting recommendations, THE System SHALL display at least 3 career options with descriptions and suitability explanations
4. WHEN a student has conflicting interests, THE AI_Engine SHALL identify hybrid career paths that combine multiple domains
5. THE AI_Engine SHALL use Generative AI models to provide natural language explanations for each recommendation
6. WHEN aptitude scores are available, THE AI_Engine SHALL weight recommendations based on demonstrated strengths

### Requirement 3: Graph-Based Career Mapping

**User Story:** As a student, I want to visualize my career journey as a dynamic graph, so that I can understand multiple pathways to my goal.

#### Acceptance Criteria

1. WHEN a student selects a career path, THE System SHALL generate a Graph with nodes representing milestones and edges representing transitions
2. THE System SHALL support multiple Routes to the same career destination
3. WHEN displaying the Graph, THE System SHALL highlight the currently recommended Route
4. WHEN a student is at a specific Milestone, THE System SHALL visually indicate their current position on the Graph
5. THE Graph SHALL include milestone types: entrance exams, certifications, skill development, college education, internships, and work experience
6. WHEN multiple Routes exist, THE System SHALL allow students to compare routes side-by-side
7. THE System SHALL render the Graph with smooth curves and animated transitions for visual clarity

### Requirement 4: Personalized Roadmap Generation

**User Story:** As a student, I want a detailed step-by-step roadmap, so that I know exactly what actions to take to reach my career goal.

#### Acceptance Criteria

1. WHEN a student selects a career and route, THE AI_Engine SHALL generate a personalized roadmap with time-sequenced milestones
2. WHEN generating a roadmap, THE System SHALL include specific exams, certifications, skills to learn, and colleges to target
3. WHEN a milestone has prerequisites, THE System SHALL order milestones to respect dependency relationships
4. WHEN displaying a milestone, THE System SHALL show estimated duration, difficulty level, and resources
5. THE System SHALL adapt milestone timing based on the student's current age and education level
6. WHEN a student is below college age, THE System SHALL include school-level preparation milestones
7. THE AI_Engine SHALL generate milestone descriptions in natural language with actionable guidance

### Requirement 5: College Matching and Recommendations

**User Story:** As a student, I want college recommendations aligned with my career path, so that I can apply to institutions that support my goals.

#### Acceptance Criteria

1. WHEN a student's roadmap includes college education, THE College_Matcher SHALL recommend colleges aligned with the selected career
2. WHEN recommending colleges, THE System SHALL consider student location preferences, academic performance, and career specialization
3. WHEN displaying college recommendations, THE System SHALL show college name, location, programs offered, and alignment score
4. THE College_Matcher SHALL rank colleges by fit score based on career path requirements
5. WHEN a student selects a college, THE System SHALL update the roadmap to reflect that choice
6. THE System SHALL support filtering colleges by location, type (government/private), and entrance exam requirements

### Requirement 6: Continuous Progress Monitoring

**User Story:** As a student, I want the system to track my progress, so that it can provide timely guidance and detect when I'm off track.

#### Acceptance Criteria

1. WHEN a student completes a milestone, THE Progress_Monitor SHALL update their position on the Graph
2. WHEN a student marks a milestone complete, THE System SHALL validate completion with evidence or confirmation
3. THE Progress_Monitor SHALL calculate completion percentage for the overall roadmap
4. WHEN a student is behind schedule, THE System SHALL send notifications with encouragement and resources
5. THE Progress_Monitor SHALL track time spent at each milestone and compare against estimated duration
6. WHEN a student achieves a milestone ahead of schedule, THE System SHALL recognize the achievement

### Requirement 7: Dynamic Re-routing

**User Story:** As a student, I want the system to recalculate my path when I face challenges or change direction, so that I can still reach my career goal through alternative routes.

#### Acceptance Criteria

1. WHEN a Deviation is detected, THE System SHALL identify alternative Routes to the same career destination
2. WHEN re-routing, THE System SHALL preserve the career destination while changing the path
3. WHEN presenting alternative routes, THE System SHALL explain why the re-route is recommended
4. WHEN a student fails an entrance exam, THE System SHALL suggest alternative college options or certification paths
5. WHEN a student changes their timeline, THE System SHALL adjust milestone scheduling accordingly
6. THE System SHALL allow students to manually request re-routing at any time
7. WHEN re-routing, THE AI_Engine SHALL consider completed milestones and avoid redundant steps

### Requirement 8: Multi-User Type Support

**User Story:** As an institution administrator, I want to manage multiple student profiles, so that I can provide career guidance at scale.

#### Acceptance Criteria

1. WHEN an institution creates an account, THE System SHALL support managing multiple student profiles
2. WHEN an institution views student data, THE System SHALL provide aggregate analytics on career preferences and progress
3. THE System SHALL support role-based access with permissions for administrators, counselors, and students
4. WHEN an institution exports data, THE System SHALL provide reports in CSV or PDF format
5. THE System SHALL maintain data privacy with student consent for institutional access

### Requirement 9: Career Switcher Support

**User Story:** As a career switcher, I want recommendations that account for my existing experience, so that I can transition efficiently to a new career.

#### Acceptance Criteria

1. WHEN a career switcher creates a profile, THE System SHALL collect current career, years of experience, and transferable skills
2. WHEN generating recommendations for career switchers, THE AI_Engine SHALL identify careers that leverage existing skills
3. WHEN creating roadmaps for career switchers, THE System SHALL skip milestones already completed through prior experience
4. THE System SHALL highlight skill gaps between current and target careers
5. WHEN recommending routes for career switchers, THE System SHALL prioritize shorter paths that build on existing knowledge

### Requirement 10: Generative AI Integration

**User Story:** As a developer, I want clear integration points for Generative AI, so that the system can leverage AI capabilities effectively.

#### Acceptance Criteria

1. THE System SHALL provide an API interface for the AI_Engine to receive student profiles and return recommendations
2. WHEN calling the AI_Engine, THE System SHALL format profile data as structured prompts with relevant context
3. THE AI_Engine SHALL return recommendations in JSON format with career IDs, titles, descriptions, and suitability scores
4. WHEN generating roadmaps, THE AI_Engine SHALL produce milestone lists with descriptions, durations, and resources
5. THE System SHALL handle AI_Engine errors gracefully and fall back to rule-based recommendations
6. THE System SHALL log AI_Engine requests and responses for quality monitoring and improvement

### Requirement 11: Data Persistence and Retrieval

**User Story:** As a student, I want my profile and progress to be saved, so that I can return to the platform and continue my journey.

#### Acceptance Criteria

1. WHEN a student creates or updates data, THE System SHALL persist it to storage immediately
2. THE System SHALL support both local storage for client-side data and backend storage for cross-device access
3. WHEN a student logs in, THE System SHALL retrieve their complete profile, selected career, and progress state
4. THE System SHALL serialize Graph structures for storage and deserialize them for rendering
5. WHEN storage operations fail, THE System SHALL notify the user and retry with exponential backoff

### Requirement 12: Visual Career Timeline

**User Story:** As a student, I want to see my career journey as a timeline, so that I can understand the chronological sequence of milestones.

#### Acceptance Criteria

1. WHEN a student views their roadmap, THE System SHALL display milestones in chronological order on a timeline
2. WHEN displaying the timeline, THE System SHALL show past, current, and future milestones with distinct visual styles
3. THE System SHALL indicate estimated dates for future milestones based on current progress
4. WHEN a student clicks a timeline milestone, THE System SHALL display detailed information and resources
5. THE System SHALL support zooming and scrolling for timelines spanning multiple years

### Requirement 13: Route Comparison

**User Story:** As a student, I want to compare different routes to my career goal, so that I can make informed decisions about my path.

#### Acceptance Criteria

1. WHEN multiple Routes exist for a career, THE System SHALL provide a comparison view
2. WHEN comparing routes, THE System SHALL display duration, difficulty, cost, and milestone differences
3. THE System SHALL highlight trade-offs between routes (e.g., faster but more expensive vs. slower but affordable)
4. WHEN a student selects a route for comparison, THE System SHALL visually overlay it on the Graph
5. THE System SHALL allow students to switch between routes without losing progress data
