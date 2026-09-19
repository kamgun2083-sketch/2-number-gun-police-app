# Police Apps — एकीकृत संग्रह

काठमाडौं उपत्यका प्रहरी सशस्त्र प्रहरी गण नं. २, महाराजगंज का सबै डिजिटल प्रणालीहरू एकै रिपोजिटरीमा।

## संरचना

| फोल्डर | प्रणाली | मूल रिपो |
|---|---|---|
| `apps/bida-management/` | बिदा व्यवस्थापन प्रणाली | bidaupdate |
| `apps/duty-system/` | कार्यालय ड्युटी व्यवस्थापन | duty-system |
| `apps/gate-pass/` | डिजिटल गेट पास प्रणाली | gatepass |
| `apps/digital-correspondence/` | डिजिटल पत्राचार तथा हस्ताक्षर | machine-digitalization |
| `apps/daily-record-form/` | दैनिक काम-कारवाही फारम | police-form |
| `apps/pt-report/` | दैनिक पिटी / रोलकल रिपोर्ट | PT-Report |
| `apps/staff-records/` | प्रहरी कर्मचारी डिजिटल अभिलेख | training- |
| `python-apps/` | Flask प्रणालीहरू (सोर्स मात्र) | police-duty, police-duty-app, police-dutyy |

`index.html` — सबै प्रणालीमा पुग्ने मुख्य पृष्ठ।

## GitHub Pages मा होस्ट गर्ने

1. GitHub मा नयाँ रिपो बनाउनुहोस् (उदाहरण: `police-apps`)।
2. यो फोल्डरबाट push गर्नुहोस्:

   ```bash
   git init -b main
   git add .
   git commit -m "Combine all police digital systems into one repo"
   git remote add origin https://github.com/<username>/police-apps.git
   git push -u origin main
   ```

3. रिपोको **Settings → Pages** मा गएर Source = `main` / `/ (root)` छान्नुहोस्।
4. केही मिनेटमा साइट `https://<username>.github.io/police-apps/` मा चल्छ।

## Python प्रणालीबारे

`python-apps/` भित्रका Flask एपहरू GitHub Pages मा **चल्दैनन्** — Pages ले static फाइल मात्र देखाउँछ।
तिनलाई होस्ट गर्न:

- **PythonAnywhere** (निःशुल्क, डाटाबेस सुरक्षित रहन्छ) — SQLite प्रयोग गर्ने भएकाले उत्तम।
- **Render** (निःशुल्क) — तर redeploy मा `database.db` मेटिन्छ।

होस्ट गर्नुअघि `Procfile` मा यो लेख्नुहोस्: `web: gunicorn app:app`
