# WT Lab Projects

## 1. AngularJS – HackPass (Registration & Login)
Folder: `1-AngularJS-Hackathon-Pass`

Open `index.html` in Chrome (needs internet for the AngularJS CDN).
Register (first name, last name, username, password), then log in to see your digital hackathon pass.

AngularJS concepts used: `ng-app`, `ng-controller` (controller-as), `ng-model`, `ng-submit`,
form validation (`required`, `ng-minlength`, `ng-maxlength`, `ng-pattern`, `$touched`, `$invalid`),
`ng-show`, `ng-if`, `ng-class`, `ng-style`, `ng-repeat`, `ng-options`, filters (`uppercase`, `date`),
and a custom `factory` service. Users are stored in the browser's localStorage.

## 2. Django – CalcLog (Calculator with saved history)
Folder: `2-Django-Calculator`

```
cd 2-Django-Calculator
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```
Open http://127.0.0.1:8000/

- `calculator/evaluator.py` – safely evaluates the expression (no `eval()`)
- `calculator/models.py` – `Calculation` model, stored in SQLite
- `calculator/views.py` – `home` (calculate + save) and `clear_history`
- `calculator/templates/calculator/home.html` – the UI
- Run the tests: `python manage.py test calculator`
- Admin panel (optional): `python manage.py createsuperuser`, then go to /admin/

## 4. Figma – Spatia (AR furniture store website)
Folder: `Figma Website`

A mobile-first furniture store where shoppers preview products in 3D and in their own room with AR,
then buy with one tap. Designed in Figma and built with Figma Make as a Next.js + Payload CMS app.

- `app/(frontend)/SpatiaApp.tsx` – the store UI (home, product, AR view, checkout)
- `app/(frontend)/api/auth/` – sign up, log in, log out and current-user routes
- `app/(payload)/` – Payload CMS admin panel (`/admin`) and REST / GraphQL API (`/api`)
- `src/payload.config.ts` and `src/collections/` – CMS configuration and collections
- `public/assets/` – room photos used in the design

To run it locally you need Node.js 24+ and pnpm, plus the Figma environment values
(`FIGMA_PUBLIC_URL`, `FIGMA_CONTENT_API_URL`, `FIGMA_CONTENT_API_CONTENT_SYSTEM_ID`, `FIGMA_OAUTH_CLIENT_ID`):

```
cd "Figma Website"
pnpm install
pnpm dev
```
The scripts use Unix-style environment variables, so run them in Git Bash (not PowerShell or cmd).
Open http://localhost:3000/

## 5. Mini Project – Constellation Memory Map
Folder: `5-Constellation-Memory-Map`

Open `index.html` in Chrome (no internet or install needed).

- Double-click the sky to drop a memory or goal star
- Drag stars close together and they're pulled into constellations with glowing lines
- Hover for a tooltip, click for details (edit, delete, mark goal achieved)
- Search, gravity and link-distance sliders, and JSON export/import are in the ⋯ menu

Tech: HTML5 Canvas, 2D vector physics in vanilla JS (spring gravity, collision repulsion,
damping, wall bounce, drag and throw), union-find to detect constellations,
CSS `backdrop-filter` glass panels, and localStorage.
