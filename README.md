# copilot-prompts-template

# 🧠 TƯ DUY CỐT LÕI TRƯỚC KHI VIẾT PROMPT

Khi framework của bạn:

- chạy **đa nền tảng** (WEB / API / MOBILE)
- hỗ trợ **nhiều kỹ thuật** (Selenium, Playwright, Appium, RestAssured, OkHttp…)
- **còn mở rộng trong tương lai**

👉 Prompt **KHÔNG được gắn vào tool cụ thể**
👉 Prompt phải **gắn vào kiến trúc + abstraction**

Nói cách khác:

> Prompt của bạn phải hỏi _“framework nên thiết kế thế nào”_
> chứ không hỏi _“viết test bằng Selenium thế nào”_

---

# 🎯 CHIẾN LƯỢC PROMPT REPO CHO GIAI ĐOẠN DESIGN FRAMEWORK

## 1️⃣ Tách PROMPT theo **TẦNG TƯ DUY**, không theo TOOL

❌ Sai hướng:

```
selenium.md
playwright.md
appium.md
```

✅ Đúng hướng:

```
architecture.md
platform-abstraction.md
execution-model.md
test-design.md
extensibility.md
```

---

# 📁 CẤU TRÚC PROMPT REPO KHUYÊN DÙNG (GIAI ĐOẠN DESIGN)

```
qa-framework-prompts/
 ├─ 00-principles.md
 ├─ 01-architecture.md
 ├─ 02-platform-abstraction.md
 ├─ 03-driver-engine.md
 ├─ 04-test-design.md
 ├─ 05-extension-strategy.md
 ├─ 06-anti-patterns.md
 └─ README.md
```

---

# 2️⃣ PROMPT NỀN TẢNG – KHÔNG BAO GIỜ THAY ĐỔI

## 📄 `00-principles.md`

```markdown
Bạn là Test Framework Architect.

Hãy tư vấn với mindset:

- Framework đa nền tảng (Web, API, Mobile)
- Không phụ thuộc tool cụ thể
- Ưu tiên abstraction, extensibility, maintainability
- Dễ mở rộng kỹ thuật mới trong tương lai
- Phù hợp team QA từ junior đến senior

Không đề xuất code gắn chặt Selenium / Playwright / Appium,
chỉ đề xuất khi cần ví dụ minh họa.

Trả lời bằng tiếng Việt.
```

👉 File này là **gốc**, các prompt khác đều kế thừa tư duy này.

---

# 3️⃣ PROMPT KIẾN TRÚC TỔNG THỂ (RẤT QUAN TRỌNG)

## 📄 `01-architecture.md`

```markdown
Bạn là Test Framework Architect.

Hãy đề xuất kiến trúc tổng thể cho một test framework:

- Hỗ trợ Web, API, Mobile
- Cho phép dùng nhiều engine khác nhau (Selenium, Playwright, Appium, RestAssured, OkHttp)
- Tách rõ:
  - test definition
  - execution engine
  - platform-specific implementation
  - shared core

Yêu cầu:

1. Giải thích kiến trúc bằng sơ đồ logic (text)
2. Nêu rõ trách nhiệm từng layer
3. Chỉ ra điểm mở rộng trong tương lai
4. Tránh coupling giữa test và tool

Trả lời bằng tiếng Việt.
```

---

# 4️⃣ PROMPT ABSTRACTION NỀN TẢNG (LINH HỒN FRAMEWORK)

## 📄 `02-platform-abstraction.md`

```markdown
Thiết kế abstraction cho test framework đa nền tảng.

Mục tiêu:

- Test case KHÔNG biết nó đang chạy Web, API hay Mobile
- Có thể thêm nền tảng mới mà không sửa test cũ

Hãy đề xuất:

- Interface / contract cần có
- Cách mapping platform → implementation
- Ví dụ minh họa (pseudo-code Java)

Trả lời bằng tiếng Việt.
```

👉 Prompt này giúp bạn **tránh design sai ngay từ đầu**.

---

# 5️⃣ PROMPT ENGINE / DRIVER (QUẢN LÝ TOOL)

## 📄 `03-driver-engine.md`

```markdown
Thiết kế layer quản lý engine / driver cho framework test.

Yêu cầu:

- Không để test phụ thuộc Selenium / Playwright / Appium
- Cho phép swap engine bằng config
- Quản lý lifecycle rõ ràng

Hãy đề xuất:

- Cách tổ chức engine layer
- Pattern phù hợp (Factory, Strategy, Adapter...)
- Ưu và nhược điểm

Trả lời bằng tiếng Việt.
```

---

# 6️⃣ PROMPT THIẾT KẾ TEST (TEST CASE KHÔNG BỊ BẨN)

## 📄 `04-test-design.md`

```markdown
Thiết kế cách viết test case cho framework đa nền tảng.

Mục tiêu:

- Test dễ đọc
- Không chứa logic kỹ thuật
- Dễ maintain khi đổi tool

Hãy đề xuất:

- Style viết test
- Cách tách test flow, assertion, data
- Ví dụ test ở mức abstract

Trả lời bằng tiếng Việt.
```

---

# 7️⃣ PROMPT MỞ RỘNG & SCALE (NHÌN XA)

## 📄 `05-extension-strategy.md`

```markdown
Framework cần mở rộng trong tương lai:

- Thêm platform mới
- Thêm engine mới
- Thêm kỹ thuật test mới (performance, security...)

Hãy đề xuất:

- Chiến lược extension
- Quy ước để team follow
- Những điểm cần khóa chặt từ đầu

Trả lời bằng tiếng Việt.
```

---

# 8️⃣ PROMPT CẢNH BÁO SAI LẦM (CỰC KỲ GIÁ TRỊ)

## 📄 `06-anti-patterns.md`

```markdown
Liệt kê những anti-pattern thường gặp khi thiết kế test framework đa nền tảng.

Ví dụ:

- Coupling test với tool
- Over-engineering
- God class
- Static everywhere

Với mỗi anti-pattern:

- Vì sao nguy hiểm
- Cách tránh ngay từ đầu
```

---

# 🔥 CÁCH DÙNG PROMPT REPO Ở GIAI ĐOẠN DESIGN

### Cách làm đúng:

1. Mỗi ngày **chỉ hỏi 1 prompt**
2. So sánh kết quả → điều chỉnh prompt
3. Ghi chú lại decision trong framework repo
4. Không code quá sớm

👉 Prompt = **người phản biện kiến trúc**, không phải code generator.

## 📄 `markdown.json` (VS Code User Snippets)

> Mở bằng:
> `Ctrl + Shift + P` → **Preferences: Configure User Snippets** → chọn **markdown.json**

```json
{
  "Framework Principles": {
    "prefix": "fw-principles",
    "body": [
      "Bạn là Test Framework Architect.",
      "",
      "Hãy tư vấn với mindset:",
      "- Framework đa nền tảng (Web, API, Mobile)",
      "- Không phụ thuộc tool cụ thể",
      "- Ưu tiên abstraction, extensibility, maintainability",
      "- Có thể mở rộng trong tương lai",
      "",
      "Trả lời bằng tiếng Việt."
    ],
    "description": "Mindset nền tảng cho thiết kế test framework"
  },

  "Framework Architecture": {
    "prefix": "fw-architecture",
    "body": [
      "Bạn là Test Framework Architect.",
      "",
      "Hãy đề xuất kiến trúc tổng thể cho test framework:",
      "- Hỗ trợ Web, API, Mobile",
      "- Cho phép nhiều engine (Selenium, Playwright, Appium, RestAssured, OkHttp...)",
      "- Tách rõ test definition, core, platform, engine",
      "",
      "Yêu cầu:",
      "1. Mô tả kiến trúc bằng sơ đồ logic (text)",
      "2. Trách nhiệm từng layer",
      "3. Điểm mở rộng trong tương lai",
      "4. Tránh coupling test với tool",
      "",
      "Trả lời bằng tiếng Việt."
    ],
    "description": "Thiết kế kiến trúc tổng thể framework đa nền tảng"
  },

  "Platform Abstraction": {
    "prefix": "fw-abstraction",
    "body": [
      "Thiết kế abstraction cho test framework đa nền tảng.",
      "",
      "Mục tiêu:",
      "- Test case KHÔNG biết đang chạy Web, API hay Mobile",
      "- Có thể thêm platform mới mà không sửa test cũ",
      "",
      "Hãy đề xuất:",
      "- Interface / contract cốt lõi",
      "- Cách mapping platform → implementation",
      "- Ví dụ pseudo-code Java nếu cần",
      "",
      "Trả lời bằng tiếng Việt."
    ],
    "description": "Thiết kế abstraction Web / API / Mobile"
  },

  "Engine Driver Design": {
    "prefix": "fw-engine",
    "body": [
      "Thiết kế layer quản lý engine / driver cho test framework.",
      "",
      "Yêu cầu:",
      "- Test không phụ thuộc Selenium / Playwright / Appium",
      "- Có thể swap engine bằng config",
      "- Quản lý lifecycle rõ ràng",
      "",
      "Hãy đề xuất:",
      "- Pattern phù hợp (Factory, Strategy, Adapter...)",
      "- Ưu / nhược điểm",
      "",
      "Trả lời bằng tiếng Việt."
    ],
    "description": "Thiết kế engine / driver layer"
  },

  "Test Design Strategy": {
    "prefix": "fw-testdesign",
    "body": [
      "Thiết kế cách viết test case cho framework đa nền tảng.",
      "",
      "Mục tiêu:",
      "- Test dễ đọc",
      "- Không chứa logic kỹ thuật",
      "- Dễ maintain khi đổi engine",
      "",
      "Hãy đề xuất:",
      "- Style viết test",
      "- Cách tách flow, assertion, data",
      "- Ví dụ test ở mức abstract",
      "",
      "Trả lời bằng tiếng Việt."
    ],
    "description": "Chiến lược thiết kế test case cho framework"
  },

  "Framework Extension Strategy": {
    "prefix": "fw-extension",
    "body": [
      "Framework cần mở rộng trong tương lai:",
      "- Thêm platform mới",
      "- Thêm engine mới",
      "- Thêm kỹ thuật test (performance, security...)",
      "",
      "Hãy đề xuất:",
      "- Chiến lược extension",
      "- Quy ước để team follow",
      "- Những điểm cần khóa chặt từ đầu",
      "",
      "Trả lời bằng tiếng Việt."
    ],
    "description": "Chiến lược scale & mở rộng framework"
  },

  "Framework Anti-Patterns": {
    "prefix": "fw-antipattern",
    "body": [
      "Liệt kê các anti-pattern khi thiết kế test framework đa nền tảng.",
      "",
      "Ví dụ:",
      "- Coupling test với tool",
      "- God class",
      "- Over-engineering",
      "- Static everywhere",
      "",
      "Với mỗi anti-pattern:",
      "- Vì sao nguy hiểm",
      "- Cách tránh ngay từ đầu",
      "",
      "Trả lời bằng tiếng Việt."
    ],
    "description": "Anti-pattern khi thiết kế test framework"
  }
}
```

---

## 🧭 CÁCH DÙNG ĐÚNG (RẤT QUAN TRỌNG)

### Ví dụ workflow thiết kế:

1. Mở **Copilot Chat**
2. Gõ: fw-antipattern
