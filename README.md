# Auto Parts Contact Form (Prototype)

A contact form prototype built as a starting point for an auto parts store website, based on what the client asked for.

> 📌 **Note:** This is a front-end sketch to align on layout and fields with the client. It has no backend, so submitting the form does not send anything yet.

## Overview

The goal was to give the client a visual base to react to before building the real site: a simple way for customers who can't find a part to leave their email and phone and get a reply with price and availability.

The first version was written in 2023. In 2026 I reviewed the code, fixed several issues, and redesigned the look.

## Preview

The layout has two panels:

- **Left:** a short message ("Não achou a peça?") with a workshop warning-stripe accent
- **Right:** the contact form with email and phone fields

On small screens the panels stack vertically.

## Features

- Responsive layout (desktop and mobile)
- Native browser validation (`type="email"`, `type="tel"`, `required`)
- Visible keyboard focus and clear error state for invalid input
- Labels linked to every field, for accessibility and screen readers
- Respects the user's "reduce motion" setting
- No JavaScript and no external dependencies

## Tech Stack

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)

## How to Run

No installation needed. Download `index.html` and open it in any browser.

## What I Fixed in the Original Version

| Original (2023) | Revised (2026) | Why it matters |
|---|---|---|
| Phone field used `type="password"` | `type="tel"` | The number was hidden and browsers treated it as a password |
| Email field used `type="text"` | `type="email"` | Built-in validation and the right mobile keyboard |
| Form had no `action` or `method` | `action` and `method="post"` | Without them, data is sent via GET and ends up in the URL and logs |
| `box-sizing: 0` (invalid value) | `box-sizing: border-box` | Inputs were overflowing the form width |
| No `<!DOCTYPE>`, `charset` or `viewport` | Added | Predictable rendering, correct accents, mobile support |
| `<style>` outside `<head>` | Moved inside `<head>` | Valid HTML structure |
| Placeholders only | Added `<label>` elements | Accessibility, and text stays visible while typing |
| JavaScript for focus colors | Pure CSS `:focus` | Less code, same result, better keyboard support |

## Next Steps (Not Implemented)

- Backend to receive and validate the submission (server-side validation is required, since browser validation can be bypassed)
- Spam protection (CAPTCHA or rate limiting) and HTTPS
- A message field and a success/error confirmation screen
- Real store branding (logo, name, colors)

## Security Notes

- Never rely only on client-side validation. Always validate and sanitize on the server.
- Use `POST` for forms that collect personal data such as email and phone, so they do not appear in the URL.
- Contact data is personal data and falls under privacy laws (such as LGPD in Brazil), so the real site will need a privacy notice and a clear purpose for collecting it.

## Author

**Nicolas Borges Ocampos**
[LinkedIn](https://www.linkedin.com/in/nicolas-borges-ocampos)

   | 2023 / 2026 | HTML/CSS | [Auto Parts Contact Form](html-css/auto-parts-contact-form) | Forms, validation, responsive layout |
