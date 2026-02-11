# Build and Test
# Build and Test

# Build and Test

**Purpose**: Build all units and execute comprehensive testing strategy
**目的**: すべてのユニットをビルドし、包括的なテスト戦略を実行する

**目的**: すべてのユニットをビルドし、包括的なテスト戦略を実行する

## Prerequisites
- Code Generation must be complete for all units
- All code artifacts must be generated
- Project is ready for build and testing
## 前提条件
- すべてのユニットで Code Generation が完了していること
- すべてのコード成果物が生成済みであること
- プロジェクトがビルドとテストの準備完了

## 前提条件
- すべてのユニットで Code Generation が完了していること
- すべてのコード成果物が生成済みであること
- プロジェクトがビルドとテストの準備完了

---
---

---

## Step 1: Analyze Testing Requirements
## ステップ 1: テスト要件の分析

## ステップ 1: テスト要件の分析

Analyze the project to determine appropriate testing strategy:
- **Unit tests**: Already generated per unit during code generation
- **Integration tests**: Test interactions between units/services
- **Performance tests**: Load, stress, and scalability testing
- **End-to-end tests**: Complete user workflows
- **Contract tests**: API contract validation between services
- **Security tests**: Vulnerability scanning, penetration testing
プロジェクトを分析して適切なテスト戦略を決定:
- **ユニットテスト**: Code Generation でユニットごとに生成済み
- **統合テスト**: ユニット/サービス間の相互作用を検証
- **性能テスト**: 負荷・ストレス・スケーラビリティ
- **E2E テスト**: 完全なユーザーワークフロー
- **契約テスト**: サービス間の API 契約検証
- **セキュリティテスト**: 脆弱性スキャン、ペネトレーション

プロジェクトを分析して適切なテスト戦略を決定:
- **ユニットテスト**: Code Generation でユニットごとに生成済み
- **統合テスト**: ユニット/サービス間の相互作用を検証
- **性能テスト**: 負荷・ストレス・スケーラビリティ
- **E2E テスト**: 完全なユーザーワークフロー
- **契約テスト**: サービス間の API 契約検証
- **セキュリティテスト**: 脆弱性スキャン、ペネトレーション

---
---

---

## Step 2: Generate Build Instructions
## ステップ 2: ビルド手順の生成

## ステップ 2: ビルド手順の生成

Create `aidlc-docs/construction/build-and-test/build-instructions.md`:
`aidlc-docs/construction/build-and-test/build-instructions.md` を作成:

`aidlc-docs/construction/build-and-test/build-instructions.md` を作成:

```markdown
# Build Instructions

## Prerequisites
- **Build Tool**: [Tool name and version]
- **Dependencies**: [List all required dependencies]
- **Environment Variables**: [List required env vars]
- **System Requirements**: [OS, memory, disk space]

## Build Steps

### 1. Install Dependencies
\`\`\`bash
[Command to install dependencies]
# Example: npm install, mvn dependency:resolve, pip install -r requirements.txt
\`\`\`

### 2. Configure Environment
\`\`\`bash
[Commands to set up environment]
# Example: export variables, configure credentials
\`\`\`

### 3. Build All Units
\`\`\`bash
[Command to build all units]
# Example: mvn clean install, npm run build, brazil-build
\`\`\`

### 4. Verify Build Success
- **Expected Output**: [Describe successful build output]
- **Build Artifacts**: [List generated artifacts and locations]
- **Common Warnings**: [Note any acceptable warnings]

## Troubleshooting

### Build Fails with Dependency Errors
- **Cause**: [Common causes]
- **Solution**: [Step-by-step fix]

### Build Fails with Compilation Errors
- **Cause**: [Common causes]
- **Solution**: [Step-by-step fix]
```
```markdown
# Build Instructions

## Prerequisites
- **Build Tool**: [Tool name and version]
- **Dependencies**: [List all required dependencies]
- **Environment Variables**: [List required env vars]
- **System Requirements**: [OS, memory, disk space]

## Build Steps

### 1. Install Dependencies
```bash
[Command to install dependencies]
# Example: npm install, mvn dependency:resolve, pip install -r requirements.txt
```

### 2. Configure Environment
```bash
[Commands to set up environment]
# Example: export variables, configure credentials
```

### 3. Build All Units
```bash
[Command to build all units]
# Example: mvn clean install, npm run build, brazil-build
```

### 4. Verify Build Success
- **Expected Output**: [Describe successful build output]
- **Build Artifacts**: [List generated artifacts and locations]
- **Common Warnings**: [Note any acceptable warnings]

## Troubleshooting

### Build Fails with Dependency Errors
- **Cause**: [Common causes]
- **Solution**: [Step-by-step fix]

### Build Fails with Compilation Errors
- **Cause**: [Common causes]
- **Solution**: [Step-by-step fix]
```

```markdown
# Build Instructions

## Prerequisites
- **Build Tool**: [Tool name and version]
- **Dependencies**: [List all required dependencies]
- **Environment Variables**: [List required env vars]
- **System Requirements**: [OS, memory, disk space]

## Build Steps

### 1. Install Dependencies
```bash
[Command to install dependencies]
# Example: npm install, mvn dependency:resolve, pip install -r requirements.txt
```

### 2. Configure Environment
```bash
[Commands to set up environment]
# Example: export variables, configure credentials
```

### 3. Build All Units
```bash
[Command to build all units]
# Example: mvn clean install, npm run build, brazil-build
```

### 4. Verify Build Success
- **Expected Output**: [Describe successful build output]
- **Build Artifacts**: [List generated artifacts and locations]
- **Common Warnings**: [Note any acceptable warnings]

## Troubleshooting

### Build Fails with Dependency Errors
- **Cause**: [Common causes]
- **Solution**: [Step-by-step fix]

### Build Fails with Compilation Errors
- **Cause**: [Common causes]
- **Solution**: [Step-by-step fix]
```

---
---

---

## Step 3: Generate Unit Test Execution Instructions
## ステップ 3: ユニットテスト実行手順の生成

## ステップ 3: ユニットテスト実行手順の生成

Create `aidlc-docs/construction/build-and-test/unit-test-instructions.md`:
`aidlc-docs/construction/build-and-test/unit-test-instructions.md` を作成:

`aidlc-docs/construction/build-and-test/unit-test-instructions.md` を作成:

```markdown
# Unit Test Execution

## Run Unit Tests

### 1. Execute All Unit Tests
\`\`\`bash
[Command to run all unit tests]
# Example: mvn test, npm test, pytest tests/unit
\`\`\`

### 2. Review Test Results
- **Expected**: [X] tests pass, 0 failures
- **Test Coverage**: [Expected coverage percentage]
- **Test Report Location**: [Path to test reports]

### 3. Fix Failing Tests
If tests fail:
1. Review test output in [location]
2. Identify failing test cases
3. Fix code issues
4. Rerun tests until all pass
```
```markdown
# Unit Test Execution

## Run Unit Tests

### 1. Execute All Unit Tests
```bash
[Command to run all unit tests]
# Example: mvn test, npm test, pytest tests/unit
```

### 2. Review Test Results
- **Expected**: [X] tests pass, 0 failures
- **Test Coverage**: [Expected coverage percentage]
- **Test Report Location**: [Path to test reports]

### 3. Fix Failing Tests
If tests fail:
1. Review test output in [location]
2. Identify failing test cases
3. Fix code issues
4. Rerun tests until all pass
```

```markdown
# Unit Test Execution

## Run Unit Tests

### 1. Execute All Unit Tests
```bash
[Command to run all unit tests]
# Example: mvn test, npm test, pytest tests/unit
```

### 2. Review Test Results
- **Expected**: [X] tests pass, 0 failures
- **Test Coverage**: [Expected coverage percentage]
- **Test Report Location**: [Path to test reports]

### 3. Fix Failing Tests
If tests fail:
1. Review test output in [location]
2. Identify failing test cases
3. Fix code issues
4. Rerun tests until all pass
```

---
---

---

## Step 4: Generate Integration Test Instructions
## ステップ 4: 統合テスト手順の生成

## ステップ 4: 統合テスト手順の生成

Create `aidlc-docs/construction/build-and-test/integration-test-instructions.md`:
`aidlc-docs/construction/build-and-test/integration-test-instructions.md` を作成:

`aidlc-docs/construction/build-and-test/integration-test-instructions.md` を作成:

```markdown
# Integration Test Instructions

## Purpose
Test interactions between units/services to ensure they work together correctly.

## Test Scenarios

### Scenario 1: [Unit A] → [Unit B] Integration
- **Description**: [What is being tested]
- **Setup**: [Required test environment setup]
- **Test Steps**: [Step-by-step test execution]
- **Expected Results**: [What should happen]
- **Cleanup**: [How to clean up after test]

### Scenario 2: [Unit B] → [Unit C] Integration
[Similar structure]

## Setup Integration Test Environment

### 1. Start Required Services
\`\`\`bash
[Commands to start services]
# Example: docker-compose up, start test database
\`\`\`

### 2. Configure Service Endpoints
\`\`\`bash
[Commands to configure endpoints]
# Example: export API_URL=http://localhost:8080
\`\`\`

## Run Integration Tests

### 1. Execute Integration Test Suite
\`\`\`bash
[Command to run integration tests]
# Example: mvn integration-test, npm run test:integration
\`\`\`

### 2. Verify Service Interactions
- **Test Scenarios**: [List key integration test scenarios]
- **Expected Results**: [Describe expected outcomes]
- **Logs Location**: [Where to check logs]

### 3. Cleanup
\`\`\`bash
[Commands to clean up test environment]
# Example: docker-compose down, stop test services
\`\`\`
```
```markdown
# Integration Test Instructions

## Purpose
Test interactions between units/services to ensure they work together correctly.

## Test Scenarios

### Scenario 1: [Unit A] → [Unit B] Integration
- **Description**: [What is being tested]
- **Setup**: [Required test environment setup]
- **Test Steps**: [Step-by-step test execution]
- **Expected Results**: [What should happen]
- **Cleanup**: [How to clean up after test]

### Scenario 2: [Unit B] → [Unit C] Integration
[Similar structure]

## Setup Integration Test Environment

### 1. Start Required Services
```bash
[Commands to start services]
# Example: docker-compose up, start test database
```

### 2. Configure Service Endpoints
```bash
[Commands to configure endpoints]
# Example: export API_URL=http://localhost:8080
```

## Run Integration Tests

### 1. Execute Integration Test Suite
```bash
[Command to run integration tests]
# Example: mvn integration-test, npm run test:integration
```

### 2. Verify Service Interactions
- **Test Scenarios**: [List key integration test scenarios]
- **Expected Results**: [Describe expected outcomes]
- **Logs Location**: [Where to check logs]

### 3. Cleanup
```bash
[Commands to clean up test environment]
# Example: docker-compose down, stop test services
```
```

```markdown
# Integration Test Instructions

## Purpose
Test interactions between units/services to ensure they work together correctly.

## Test Scenarios

### Scenario 1: [Unit A] → [Unit B] Integration
- **Description**: [What is being tested]
- **Setup**: [Required test environment setup]
- **Test Steps**: [Step-by-step test execution]
- **Expected Results**: [What should happen]
- **Cleanup**: [How to clean up after test]

### Scenario 2: [Unit B] → [Unit C] Integration
[Similar structure]

## Setup Integration Test Environment

### 1. Start Required Services
```bash
[Commands to start services]
# Example: docker-compose up, start test database
```

### 2. Configure Service Endpoints
```bash
[Commands to configure endpoints]
# Example: export API_URL=http://localhost:8080
```

## Run Integration Tests

### 1. Execute Integration Test Suite
```bash
[Command to run integration tests]
# Example: mvn integration-test, npm run test:integration
```

### 2. Verify Service Interactions
- **Test Scenarios**: [List key integration test scenarios]
- **Expected Results**: [Describe expected outcomes]
- **Logs Location**: [Where to check logs]

### 3. Cleanup
```bash
[Commands to clean up test environment]
# Example: docker-compose down, stop test services
```
```

---
---

---

## Step 5: Generate Performance Test Instructions (If Applicable)
## ステップ 5: 性能テスト手順の生成（該当する場合）

## ステップ 5: 性能テスト手順の生成（該当する場合）

Create `aidlc-docs/construction/build-and-test/performance-test-instructions.md`:
`aidlc-docs/construction/build-and-test/performance-test-instructions.md` を作成:

`aidlc-docs/construction/build-and-test/performance-test-instructions.md` を作成:

```markdown
# Performance Test Instructions

## Purpose
Validate system performance under load to ensure it meets requirements.

## Performance Requirements
- **Response Time**: < [X]ms for [Y]% of requests
- **Throughput**: [X] requests/second
- **Concurrent Users**: Support [X] concurrent users
- **Error Rate**: < [X]%

## Setup Performance Test Environment

### 1. Prepare Test Environment
\`\`\`bash
[Commands to set up performance testing]
# Example: scale services, configure load balancers
\`\`\`

### 2. Configure Test Parameters
- **Test Duration**: [X] minutes
- **Ramp-up Time**: [X] seconds
- **Virtual Users**: [X] users

## Run Performance Tests

### 1. Execute Load Tests
\`\`\`bash
[Command to run load tests]
# Example: jmeter -n -t test.jmx, k6 run script.js
\`\`\`

### 2. Execute Stress Tests
\`\`\`bash
[Command to run stress tests]
# Example: gradually increase load until failure
\`\`\`

### 3. Analyze Performance Results
- **Response Time**: [Actual vs Expected]
- **Throughput**: [Actual vs Expected]
- **Error Rate**: [Actual vs Expected]
- **Bottlenecks**: [Identified bottlenecks]
- **Results Location**: [Path to performance reports]

## Performance Optimization

If performance doesn't meet requirements:
1. Identify bottlenecks from test results
2. Optimize code/queries/configurations
3. Rerun tests to validate improvements
```
```markdown
# Performance Test Instructions

## Purpose
Validate system performance under load to ensure it meets requirements.

## Performance Requirements
- **Response Time**: < [X]ms for [Y]% of requests
- **Throughput**: [X] requests/second
- **Concurrent Users**: Support [X] concurrent users
- **Error Rate**: < [X]%

## Setup Performance Test Environment

### 1. Prepare Test Environment
```bash
[Commands to set up performance testing]
# Example: scale services, configure load balancers
```

### 2. Configure Test Parameters
- **Test Duration**: [X] minutes
- **Ramp-up Time**: [X] seconds
- **Virtual Users**: [X] users

## Run Performance Tests

### 1. Execute Load Tests
```bash
[Command to run load tests]
# Example: jmeter -n -t test.jmx, k6 run script.js
```

### 2. Execute Stress Tests
```bash
[Command to run stress tests]
# Example: gradually increase load until failure
```

### 3. Analyze Performance Results
- **Response Time**: [Actual vs Expected]
- **Throughput**: [Actual vs Expected]
- **Error Rate**: [Actual vs Expected]
- **Bottlenecks**: [Identified bottlenecks]
- **Results Location**: [Path to performance reports]

## Performance Optimization

If performance doesn't meet requirements:
1. Identify bottlenecks from test results
2. Optimize code/queries/configurations
3. Rerun tests to validate improvements
```

```markdown
# Performance Test Instructions

## Purpose
Validate system performance under load to ensure it meets requirements.

## Performance Requirements
- **Response Time**: < [X]ms for [Y]% of requests
- **Throughput**: [X] requests/second
- **Concurrent Users**: Support [X] concurrent users
- **Error Rate**: < [X]%

## Setup Performance Test Environment

### 1. Prepare Test Environment
```bash
[Commands to set up performance testing]
# Example: scale services, configure load balancers
```

### 2. Configure Test Parameters
- **Test Duration**: [X] minutes
- **Ramp-up Time**: [X] seconds
- **Virtual Users**: [X] users

## Run Performance Tests

### 1. Execute Load Tests
```bash
[Command to run load tests]
# Example: jmeter -n -t test.jmx, k6 run script.js
```

### 2. Execute Stress Tests
```bash
[Command to run stress tests]
# Example: gradually increase load until failure
```

### 3. Analyze Performance Results
- **Response Time**: [Actual vs Expected]
- **Throughput**: [Actual vs Expected]
- **Error Rate**: [Actual vs Expected]
- **Bottlenecks**: [Identified bottlenecks]
- **Results Location**: [Path to performance reports]

## Performance Optimization

If performance doesn't meet requirements:
1. Identify bottlenecks from test results
2. Optimize code/queries/configurations
3. Rerun tests to validate improvements
```

---
---

---

## Step 6: Generate Additional Test Instructions (As Needed)
## ステップ 6: 追加テスト手順の生成（必要に応じて）

## ステップ 6: 追加テスト手順の生成（必要に応じて）

Based on project requirements, generate additional test instruction files:
プロジェクト要件に基づいて追加の手順ファイルを作成:

プロジェクト要件に基づいて追加の手順ファイルを作成:

### Contract Tests (For Microservices)
Create `aidlc-docs/construction/build-and-test/contract-test-instructions.md`:
- API contract validation between services
- Consumer-driven contract testing
- Schema validation
### 契約テスト（マイクロサービス向け）
`aidlc-docs/construction/build-and-test/contract-test-instructions.md` を作成:
- サービス間の API 契約検証
- コンシューマ駆動契約テスト
- スキーマ検証

### 契約テスト（マイクロサービス向け）
`aidlc-docs/construction/build-and-test/contract-test-instructions.md` を作成:
- サービス間の API 契約検証
- コンシューマ駆動契約テスト
- スキーマ検証

### Security Tests
Create `aidlc-docs/construction/build-and-test/security-test-instructions.md`:
- Vulnerability scanning
- Dependency security checks
- Authentication/authorization testing
- Input validation testing
### セキュリティテスト
`aidlc-docs/construction/build-and-test/security-test-instructions.md` を作成:
- 脆弱性スキャン
- 依存関係セキュリティチェック
- 認証/認可テスト
- 入力検証テスト

### セキュリティテスト
`aidlc-docs/construction/build-and-test/security-test-instructions.md` を作成:
- 脆弱性スキャン
- 依存関係セキュリティチェック
- 認証/認可テスト
- 入力検証テスト

### End-to-End Tests
Create `aidlc-docs/construction/build-and-test/e2e-test-instructions.md`:
- Complete user workflow testing
- Cross-service scenarios
- UI testing (if applicable)
### E2E テスト
`aidlc-docs/construction/build-and-test/e2e-test-instructions.md` を作成:
- 完全なユーザーワークフローテスト
- クロスサービスシナリオ
- UI テスト（該当する場合）

### E2E テスト
`aidlc-docs/construction/build-and-test/e2e-test-instructions.md` を作成:
- 完全なユーザーワークフローテスト
- クロスサービスシナリオ
- UI テスト（該当する場合）

---
---

---

## Step 7: Generate Test Summary
## ステップ 7: テストサマリーの生成

## ステップ 7: テストサマリーの生成

Create `aidlc-docs/construction/build-and-test/build-and-test-summary.md`:
`aidlc-docs/construction/build-and-test/build-and-test-summary.md` を作成:

`aidlc-docs/construction/build-and-test/build-and-test-summary.md` を作成:

```markdown
# Build and Test Summary

## Build Status
- **Build Tool**: [Tool name]
- **Build Status**: [Success/Failed]
- **Build Artifacts**: [List artifacts]
- **Build Time**: [Duration]

## Test Execution Summary

### Unit Tests
- **Total Tests**: [X]
- **Passed**: [X]
- **Failed**: [X]
- **Coverage**: [X]%
- **Status**: [Pass/Fail]

### Integration Tests
- **Test Scenarios**: [X]
- **Passed**: [X]
- **Failed**: [X]
- **Status**: [Pass/Fail]

### Performance Tests
- **Response Time**: [Actual] (Target: [Expected])
- **Throughput**: [Actual] (Target: [Expected])
- **Error Rate**: [Actual] (Target: [Expected])
- **Status**: [Pass/Fail]

### Additional Tests
- **Contract Tests**: [Pass/Fail/N/A]
- **Security Tests**: [Pass/Fail/N/A]
- **E2E Tests**: [Pass/Fail/N/A]

## Overall Status
- **Build**: [Success/Failed]
- **All Tests**: [Pass/Fail]
- **Ready for Operations**: [Yes/No]

## Next Steps
[If all pass]: Ready to proceed to Operations phase for deployment planning
[If failures]: Address failing tests and rebuild
```
```markdown
# Build and Test Summary

## Build Status
- **Build Tool**: [Tool name]
- **Build Status**: [Success/Failed]
- **Build Artifacts**: [List artifacts]
- **Build Time**: [Duration]

## Test Execution Summary

### Unit Tests
- **Total Tests**: [X]
- **Passed**: [X]
- **Failed**: [X]
- **Coverage**: [X]%
- **Status**: [Pass/Fail]

### Integration Tests
- **Test Scenarios**: [X]
- **Passed**: [X]
- **Failed**: [X]
- **Status**: [Pass/Fail]

### Performance Tests
- **Response Time**: [Actual] (Target: [Expected])
- **Throughput**: [Actual] (Target: [Expected])
- **Error Rate**: [Actual] (Target: [Expected])
- **Status**: [Pass/Fail]

### Additional Tests
- **Contract Tests**: [Pass/Fail/N/A]
- **Security Tests**: [Pass/Fail/N/A]
- **E2E Tests**: [Pass/Fail/N/A]

## Overall Status
- **Build**: [Success/Failed]
- **All Tests**: [Pass/Fail]
- **Ready for Operations**: [Yes/No]

## Next Steps
[If all pass]: Ready to proceed to Operations phase for deployment planning
[If failures]: Address failing tests and rebuild
```

```markdown
# Build and Test Summary

## Build Status
- **Build Tool**: [Tool name]
- **Build Status**: [Success/Failed]
- **Build Artifacts**: [List artifacts]
- **Build Time**: [Duration]

## Test Execution Summary

### Unit Tests
- **Total Tests**: [X]
- **Passed**: [X]
- **Failed**: [X]
- **Coverage**: [X]%
- **Status**: [Pass/Fail]

### Integration Tests
- **Test Scenarios**: [X]
- **Passed**: [X]
- **Failed**: [X]
- **Status**: [Pass/Fail]

### Performance Tests
- **Response Time**: [Actual] (Target: [Expected])
- **Throughput**: [Actual] (Target: [Expected])
- **Error Rate**: [Actual] (Target: [Expected])
- **Status**: [Pass/Fail]

### Additional Tests
- **Contract Tests**: [Pass/Fail/N/A]
- **Security Tests**: [Pass/Fail/N/A]
- **E2E Tests**: [Pass/Fail/N/A]

## Overall Status
- **Build**: [Success/Failed]
- **All Tests**: [Pass/Fail]
- **Ready for Operations**: [Yes/No]

## Next Steps
[If all pass]: Ready to proceed to Operations phase for deployment planning
[If failures]: Address failing tests and rebuild
```

---
---

---

## Step 8: Update State Tracking
## ステップ 8: 状態追跡の更新

## ステップ 8: 状態追跡の更新

Update `aidlc-docs/aidlc-state.md`:
- Mark Build and Test stage as complete
- Update current status
`aidlc-docs/aidlc-state.md` を更新:
- Build and Test ステージを完了にする
- 現在状況を更新

`aidlc-docs/aidlc-state.md` を更新:
- Build and Test ステージを完了にする
- 現在状況を更新

---
---

---

## Step 9: Present Results to User
## ステップ 9: 結果の提示

## ステップ 9: 結果の提示

Present comprehensive message:
包括的メッセージを提示:

包括的メッセージを提示:

```
"🔨 Build and Test Complete!

**Build Status**: [Success/Failed]

**Test Results**:
✅ Unit Tests: [X] passed
✅ Integration Tests: [X] scenarios passed
✅ Performance Tests: [Status]
✅ Additional Tests: [Status]

**Generated Files**:
1. ✅ build-instructions.md
2. ✅ unit-test-instructions.md
3. ✅ integration-test-instructions.md
4. ✅ performance-test-instructions.md (if applicable)
5. ✅ [additional test files as needed]
6. ✅ build-and-test-summary.md

Review the summary in aidlc-docs/construction/build-and-test/build-and-test-summary.md

**Ready to proceed to Operations stage for deployment planning?""
```
```
"🔨 Build and Test Complete!

**Build Status**: [Success/Failed]

**Test Results**:
✅ Unit Tests: [X] passed
✅ Integration Tests: [X] scenarios passed
✅ Performance Tests: [Status]
✅ Additional Tests: [Status]

**Generated Files**:
1. ✅ build-instructions.md
2. ✅ unit-test-instructions.md
3. ✅ integration-test-instructions.md
4. ✅ performance-test-instructions.md (if applicable)
5. ✅ [additional test files as needed]
6. ✅ build-and-test-summary.md

Review the summary in aidlc-docs/construction/build-and-test/build-and-test-summary.md

**Ready to proceed to Operations stage for deployment planning?""
```

```
"🔨 Build and Test Complete!

**Build Status**: [Success/Failed]

**Test Results**:
✅ Unit Tests: [X] passed
✅ Integration Tests: [X] scenarios passed
✅ Performance Tests: [Status]
✅ Additional Tests: [Status]

**Generated Files**:
1. ✅ build-instructions.md
2. ✅ unit-test-instructions.md
3. ✅ integration-test-instructions.md
4. ✅ performance-test-instructions.md (if applicable)
5. ✅ [additional test files as needed]
6. ✅ build-and-test-summary.md

Review the summary in aidlc-docs/construction/build-and-test/build-and-test-summary.md

**Ready to proceed to Operations stage for deployment planning?""
```

---
---

---

## Step 10: Log Interaction
## ステップ 10: 取り扱いの記録

## ステップ 10: 取り扱いの記録

**MANDATORY**: Log the phase completion in `aidlc-docs/audit.md`:
**必須**: `aidlc-docs/audit.md` にフェーズ完了を記録:

**必須**: `aidlc-docs/audit.md` にフェーズ完了を記録:

```markdown
## Build and Test Stage
**Timestamp**: [ISO timestamp]
**Build Status**: [Success/Failed]
**Test Status**: [Pass/Fail]
**Files Generated**:
- build-instructions.md
- unit-test-instructions.md
- integration-test-instructions.md
- performance-test-instructions.md
- build-and-test-summary.md

---
```
```markdown
## Build and Test Stage
**Timestamp**: [ISO timestamp]
**Build Status**: [Success/Failed]
**Test Status**: [Pass/Fail]
**Files Generated**:
- build-instructions.md
- unit-test-instructions.md
- integration-test-instructions.md
- performance-test-instructions.md
- build-and-test-summary.md

---
```

```markdown
## Build and Test Stage
**Timestamp**: [ISO timestamp]
**Build Status**: [Success/Failed]
**Test Status**: [Pass/Fail]
**Files Generated**:
- build-instructions.md
- unit-test-instructions.md
- integration-test-instructions.md
- performance-test-instructions.md
- build-and-test-summary.md

---
```
