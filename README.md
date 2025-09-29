# junk


public/locales
  /en
    header.json
    navbar.json
    unitConverter.json
    caseConverter.json
    wordCounter.json
    jsonFormatter.json
    colorPicker.json
    qrGenerator.json
  /hi
    header.json
    navbar.json
    unitConverter.json
    caseConverter.json
    wordCounter.json
    jsonFormatter.json
    colorPicker.json
    qrGenerator.json


import i18n from "i18next";
import { initReactI18next } from "react-i18next";
import HttpBackend from "i18next-http-backend";
import LanguageDetector from "i18next-browser-languagedetector";

i18n
    .use(HttpBackend) // load translation files
    .use(LanguageDetector) // detect user language
    .use(initReactI18next) // connect with React
    .init({
        fallbackLng: "en",
        debug: true,
        interpolation: {
            escapeValue: false
        },
        backend: {
            loadPath: "/locales/{{lng}}/{{ns}}.json" // path to JSONs
        },
        ns: ["header", "navbar", "unitConverter", "caseConverter", "wordCounter", "jsonFormatter", "colorPicker", "qrGenerator"],
        defaultNS: "header"
    });

export default i18n;

thats how my i18 setup is.
