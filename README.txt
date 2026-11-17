BibleIQ policy website
======================

Files
  index.html     home page (links to the two documents)
  privacy.html   privacy policy   <- the link Google Play asks for
  terms.html     terms of service <- the link for your trader declaration
  style.css, logo.svg, fonts/     design files (keep them next to the pages)

1) Fill in your details (Mac Terminal; open the folder first: cd path/to/policy-site)
   Replace the values in quotes with yours, then run each line:

   sed -i '' 's|<mark>\[Your full name or business name\]</mark>|Your Name|g' *.html
   sed -i '' 's|<mark>\[your email address\]</mark>|you@example.com|g' *.html
   sed -i '' 's|mailto:your-email|mailto:you@example.com|g' *.html
   sed -i '' 's|<mark>\[your country\]</mark>|Ghana|g' *.html
   sed -i '' 's|<mark>\[2 months / 14 months\]</mark>|14 months|g' privacy.html
   sed -i '' 's|<mark>\[your business or contact address\]</mark>|Your address|g' terms.html
   sed -i '' 's|<mark>\[your phone number\]</mark>|+233 00 000 0000|g' terms.html

   Check nothing is left (it should print 0 for each file):
   grep -c "\[Your\|\[your\|\[2 months\|your-email" *.html

   Or open each .html file in any text editor and edit the highlighted [placeholders] by hand.
   Note: the address and phone in terms.html are shown publicly if you are declared as a trader.

2) Put it online (free)
   Netlify Drop:  go to app.netlify.com/drop and drag the whole folder in. You get a link at once.
   GitHub Pages:  create a public repository, upload these files, then Settings > Pages > Deploy from branch.
   Either way your privacy policy link will look like  https://your-site/privacy.html

3) Use the links
   Play Console > App content > Privacy policy      -> https://your-site/privacy.html
   Play Console trader declaration / store listing  -> https://your-site/terms.html
   Inside the app, set PRIVACY_POLICY_URL (and TERMS_OF_USE_URL) in AppConfig.kt

Review the texts once; they are a starting point, not legal advice.
