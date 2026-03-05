# 📚 Library Management System - Quality Assurance Showcase

## 📖 Overview
This project is a comprehensive **Library Management System** developed with a primary focus on **Software Quality Assurance (SQA)** and robust **Unit Testing**. As an SQA professional, I have designed this testing suite to showcase my ability to implement rigorous tests, ensure high code coverage, and apply varied testing methodologies to validate complex back-end Java logic.

## 🎯 Quality Assurance Highlights
- **100% Core Logic Coverage**: Every critical class, service, and utility in the system has a corresponding, dedicated test class. By separating tests mirroring the package structure, the QA strategy ensures unit isolation.
- **Fail-Safe Verifications**: Implemented tests specifically for edge cases, boundary values, and negative user scenarios (e.g., negative book quantities, overflow returns, blocking invalid reservations, etc.).
- **State-Based Verification**: Validated continuous systemic state changes across workflows such as library inventory syncs, user borrowing limits, and dynamic fine calculations.

## 🛠️ Testing Tools & Tech Stack
- **Language**: Java 21
- **Testing Framework**: JUnit 5 (Jupiter API, Params, Engine) for reliable assertions and test life-cycle management
- **Build Tool**: Maven

## 📊 Testing Methodologies Applied
1. **Boundary Value Analysis (BVA)**
   - Validated critical operational limits, covering scenarios such as `testDecreaseQuantityBelowZero()`, borrowing books with zero initial available quantities, and returning books when a library's inventory configuration is already at maximum capacity.
2. **Positive & Negative Path Testing**
   - Ensured valid operational inputs ("Happy Paths") execute flawlessly, while invalid or unexpected runtime attempts (e.g., attempting to borrow unavailable books, unauthorized admin behaviors, or corrupted states) are gracefully intercepted, handled, and asserted.
3. **Equivalence Partitioning**
   - Book categories, fine rates, user hierarchies (Student vs. Librarian vs. Admin), and borrowing restrictions are thoroughly isolated and tested within valid partition brackets to guarantee system rules engine integrity.

## 🧪 Test Suite Structure
The test suite structure explicitly maps tests against the application, verifying operations across all tiers:
- **Core Models**: `BookTest`, `UserTest`, `StudentTest`, `LibrarianTest`, `AdminTest`
- **Business Logic Services**: `LibraryTest`, `AuthenticationServiceTest`, `ReservationTest`, `TransactionTest`
- **Helper Utilities**: `DateUtilsTest`, `IDGeneratorTest`, `FineCalculatorTest`, `FileManagerTest`, `ReportGeneratorTest`

## 🚀 How to Run the Tests
To execute the complete test suite and verify the system's reliability, execute the following command:

```bash
# Clean previous builds and run all JUnit 5 tests
mvn clean test
```

## 📝 Example Test Case: `BookTest.java` (Excerpts)
A brief snapshot of the rigorous methodologies applied during the implementation:
- `testBorrowBookUntilFailure()`: Asserts that a book's quantity stringently stops at exactly 0, preventing logical underflows in inventory.
- `testNegativeIncreaseAndDecreaseQuantity()`: Ensures system stability against erroneous or dynamically injected negative modifications.
- `testReturnBookWhenAlreadyAtMax()`: Pre-emptively halts integer overflow or inventory synchronization mismatch during unexpected multi-return sequences.

---
*This repository serves as a portfolio demonstration of my commitment to delivering defect-free, reliable, and fundamentally maintainable software through industry-standard rigorous Quality Assurance practices.*
