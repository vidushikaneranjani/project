# project
class Candidate {
    - name: String
    - email: String
    - password: String
    + signUp(): void
    + login(): void
    + createProfile(): void
    + upgradeProfile(): void
}

class JobProvider {
    - name: String
    - email: String
    - password: String
    - companyName: String
    - address: String
    - contactNumber: String
    - companyURL: String
    + signUp(): void
    + login(): void
    + createProfile(): void
    + updateProfile(): void
    + viewApplicants(): void
    + selectCandidates(): void
}

class Admin {
    + createJobProviderProfile(): void
    + updateJobProviderProfile(): void
    + removeInactiveProfile(): void
    + pushAdvertisement(): void
}

class Feedback {
    - message: String
    + sendFeedback(): void
}

class JobAds {
    - jobTitle: String
    - jobDescription: String
    - vacancies: int
    + pushAd(): void
    + matchVacancies(): void
    + viewJobDescription(): void
    + applyForJob(): void
}

class SignUpLogin {
    + signUpUser(): void
    + loginUser(): void
}

class RecommendingSystem {
    + recommendJobs(): void
}

class ProfileDeveloper {
    + checkProfile(): void
    + removeInactiveProfile(): void
    + provideFeedback(): void
}

class Aggregation {
    - candidate: Candidate
    - jobProvider: JobProvider
    - admin: Admin
    - feedback: Feedback
    - jobAds: JobAds
    - signUpLogin: SignUpLogin
    - recommendingSystem: RecommendingSystem
    - profileDeveloper: ProfileDeveloper
}

Candidate "1" *-- "1" SignUpLogin
Candidate "1" -- "*" Feedback
Candidate "1" -- "1" JobAds
JobProvider "1" -- "*" JobAds
Admin "1" -- "*" JobProvider
ProfileDeveloper "1" -- "*" Candidate
ProfileDeveloper "1" -- "*" JobProvider
RecommendingSystem "1" -- "*" JobAds
JobProvider "1" *-- "1" RecommendingSystem
ProfileDeveloper "1" *-- "1" JobAds
JobProvider "1" *-- "1" Admin
JobProvider "1" *-- "*" Candidate
Admin "1" *-- "*" JobAds
SignUpLogin "1" -- "1" JobAds
