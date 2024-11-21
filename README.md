<h1>Flutter Clean Architecture Project</h1>

<p>
  This project demonstrates a <strong>Clean Architecture</strong> implementation for a Flutter app. 
  Clean Architecture separates concerns across multiple layers, making your app more maintainable, testable, and scalable. 
  Each layer has a specific responsibility, ensuring minimal coupling and clear boundaries.
</p>

<h2>Project Overview</h2>
<p>This app follows the Clean Architecture principles, divided into the following layers:</p>
<ul>
  <li><strong>Presentation Layer</strong>: Responsible for the UI and user interaction. Uses <code>Widgets</code>, <code>State Management</code>, and <code>FutureBuilder</code>.</li>
  <li><strong>Domain Layer</strong>: Contains the business logic, including <strong>Entities</strong>, <strong>Use Cases</strong>, and <strong>Repository Interfaces</strong>.</li>
  <li><strong>Data Layer</strong>: Manages data sources (e.g., APIs, databases) and contains <strong>Repository Implementations</strong> and <strong>Data Transfer Objects (DTOs)</strong>.</li>
</ul>

<h2>Key Features</h2>
<ul>
  <li>Follows Clean Architecture for modularity and scalability.</li>
  <li>Service Locator (<code>GetIt</code>) for Dependency Injection.</li>
  <li><code>FutureBuilder</code> for asynchronous data fetching.</li>
  <li>Local and remote data sources for extensibility.</li>
  <li>Uses <code>dartz</code> for functional programming with <code>Either</code> types.</li>
  <li>Implements reusable and testable <strong>Use Cases</strong>.</li>
</ul>

<h2>Source Tree</h2>
<p>Here’s the folder structure for the project:</p>
<pre>
<code>
lib/
├── core/                         # Shared code across the app
│   ├── errors/                   # Custom Failure classes
│   │   └── failure.dart
│   └── usecases/                 # Base use case structure
│       └── usecase.dart
│   
├── data/                         # Data Layer: Handles data sources and repository implementation
│   ├── datasources/
│   │   ├── local_user_data_source.dart
│   │   └── remote_user_data_source.dart
│   ├── models/
│   │   └── user_model.dart       # Data Transfer Object (DTO)
│   └── repositories/
│       └── user_repository_impl.dart
│
├── domain/                       # Domain Layer: Business logic and core entities
│   ├── entities/
│   │   └── user.dart             # Core entity
│   ├── repositories/
│   │   └── user_repository.dart  # Abstract repository
│   └── usecases/
│       └── get_user_usecase.dart
│
├── presentation/                 # Presentation Layer: UI and interaction logic
│   ├── screens/
│   │   └── user_screen.dart      # Example screen
│   └── widgets/                  # Reusable widgets
│
├── service_locator.dart          # Dependency injection setup with GetIt
└── main.dart                     # App entry point
</code>
</pre>

<h2>Getting Started</h2>

<h3>Prerequisites</h3>
<p>Before running the app, ensure you have the following installed:</p>
<ul>
  <li>Flutter SDK: <a href="https://flutter.dev/docs/get-started/install" target="_blank">Install Flutter</a></li>
  <li>Dart: Comes with Flutter</li>
  <li>Dependency Manager: <code>GetIt</code></li>
</ul>

<h3>Setup</h3>
<ol>
  <li>Clone the repository:
    <pre><code>git clone https://github.com/your-username/your-repo.git
cd your-repo
    </code></pre>
  </li>
  <li>Install dependencies:
    <pre><code>flutter pub get</code></pre>
  </li>
  <li>Setup Service Locator in <code>main.dart</code>:
    <pre><code>void main() {
  setup(); // Initialize dependencies
  runApp(MyApp());
}
    </code></pre>
  </li>
  <li>Run the app:
    <pre><code>flutter run</code></pre>
  </li>
</ol>

<h2>Usage</h2>
<ul>
  <li><strong>Dependency Injection</strong>: Service Locator (<code>sl</code>) manages instances of <code>UserRepository</code>, <code>LocalUserDataSource</code>, and <code>RemoteUserDataSource</code>.</li>
  <li><strong>Domain Layer</strong>: Use cases like <code>GetUserUseCase</code> interact with the repository to fetch user data.</li>
  <li><strong>Data Layer</strong>: Switch between local and remote data sources for flexibility.</li>
</ul>

<h2>Dependencies</h2>
<p>This project uses the following packages:</p>
<ul>
  <li><code>get_it</code>: Service Locator for dependency injection.</li>
  <li><code>dartz</code>: Functional programming utilities.</li>
  <li><code>Dio</code>: Handles remote API calls.</li>
</ul>

<h2>Contributing</h2>
<p>Contributions are welcome! Please submit a pull request or open an issue for any improvements or bug fixes.</p>
