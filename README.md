以下のリンクをブックマークがある場所（ブックマークサイドバーやブックマークツールバーなど）にドラッグ＆ドロップして、ブックマークに追加してください。

<a title="sample" target="_blank" href='javascript: (function () {    class Amazon {        static getAsin() {            let ASIN = "";            const $lis = document.querySelectorAll("div.content ul li");            $lis.forEach(($li) => {                const regExp = /ASIN: [\w\d]+/;                const text = $li.textContent.trim();                if (!text.match(regExp)) {                    return false                }                ASIN = text.replace("ASIN:", "").trim()            });            return ASIN        }        static getTitle() {            const $ebooksProductTitle = document.getElementById("ebooksProductTitle");            return $ebooksProductTitle.textContent.trim()        }        static getLocale() {            return "JP"        }    }    const shortCode = "[amazonjs asin=\"${ASIN}\" locale=\"${locale}\" title=\"${title}\"]"        .replace("${ASIN}", Amazon.getAsin())        .replace("${locale}", Amazon.getLocale())        .replace("${title}", Amazon.getTitle());    alert(shortCode);})();'>sample</a>

コードの内容はは[sample.js](sample.js)をご参照ください。