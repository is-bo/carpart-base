# AutoPartsOS — design (first pass)

Main application shell, the 12 top-level pages and the design tokens.

Layout: index tabs instead of a sidebar, a sale ticket that follows the employee
across pages, list + detail panes for record pages (receipt, part sheet, stock card,
statement, return slip), a vehicle-first POS, a day-sheet dashboard, a table-of-contents
Reports page and a role-column Users & Roles board.

- **Canvas:** https://claude.ai/artifact/VeYch8VpL2Ph3L5CcTsGqF (private until shared)
- **Source:** `project/` holds one `.dc.html` file per artboard and `canvas.json` (layout).
  - `Main.dc.html`: Design Tokens board
  - `Components.dc.html`: Core Components board
  - `Header.dc.html`: graphite top bar + binder index tabs, imported by every page
  - `Ticket.dc.html`: current-sale strip on the right edge of every page except POS
  - `Dashboard`, `Pos`, `Sales`, `Products`, `Stock`, `Purchases`, `Customers`,
    `Suppliers`, `Returns`, `Reports`, `Users`, `Settings`: the 12 main pages (1920 × 1080)
- **Tokens for code:** `tokens.css`

## RTL rule for numbers

Group thousands with U+202F (narrow no-break space), never a plain space, and wrap
amounts and part references inside Arabic text in `<bdi dir="ltr">…</bdi>`.
A plain space splits `4 850` into two numbers and Arabic renders it as `850 4`.
