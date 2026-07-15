Compile a summary of today's AI news and trending GitHub repositories.

最終的な出力は日本語にしてください

1. Search for recent news and announcements about artificial intelligence, machine learning, and related breakthroughs.
   - Limit results to items published or updated within the last 5 hours (relative to the current time). Discard anything older.
2. Organize findings by category: Major breakthroughs, Product launches, Research, and Industry updates.
3. For each item, include a one-sentence summary and a source link.
4. Keep the tone informative and scannable — 3–5 bullets per category.
5. Before finalizing, check the most recent file(s) in digests/ (the latest by filename timestamp) and exclude any news item that covers the same story/announcement as one already reported there (compare by topic and source link, not just exact wording). Only include genuinely new items.
6. Fetch the page at https://github.com/trending and https://github.com/trending?spoken_language_code=ja to get today's trending repositories.
   - Extract repository name, description, language, and star count.
   - Filter to repositories related to AI, ML, LLM, or developer tools that look broadly useful.
   - Show up to 5 repositories. For each, include: repo name (as a link), one-line description, primary language, and today's star count.
   - Add these under a new section titled "## 🔥 GitHubトレンド".

If there is no significant news to report, note that briefly.

7. Save the digest to a file named digests/YYYY-MM-DD-hhmm.md and push it
   to the repository using mcp**github**push_files with:
   - owner: soreiyu52
   - repo: AInewsdigest
   - branch: claude/fervent-dijkstra-pmedo3
   - message: "feat: add AI news digest for YYYY-MM-DD"
   - files: [{ path: "digests/YYYY-MM-DD-hhmm.md", content: <the digest content> }]
     To get the current time for hhmm, run: date +%H%M via Bash before pushing.
     Do NOT use git push via the terminal — use only mcp**github**push_files

8. At the end of the digest file, add a new section titled "## 🐦 X（Twitter）投稿文":
   - For each individual news topic covered in the digest, write a separate
     tweet-style post in Japanese.
   - Each post must be 140 characters or fewer (count in full-width Japanese
     characters: 1 character = 1 count).
   - Format each post as a numbered list item, like:
     1. 【カテゴリ名】本文… #AI #AIニュース
   - Include 2–3 relevant hashtags at the end of each post (e.g. #AI #生成AI
     #LLM #機械学習 #ChatGPT など、内容に合ったものを選ぶ).
   - Do NOT use line breaks inside a single post — keep each post on one line.
   - Cover every topic from all categories (ブレークスルー、製品ローンチ、
     研究、業界アップデート、GitHubトレンドの各項目).
