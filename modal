"use strict";

(() => {
    // Определение вспомогательных функций и констант
    var gt = Object.defineProperty;
    var St = (t, e, o) => e in t ? gt(t, e, { enumerable: !0, configurable: !0, writable: !0, value: o }) : t[e] = o;
    var X = (t, e, o) => (St(t, typeof e != "symbol" ? e + "" : e, o), o);
    var d = "fs-attributes";
    var z = "animation";
    var Q = "cmsattribute";
    var T = "modal";
    var D = "support";

    // Утилитарные функции
    var g = (t, e, o, i) => t ? (t.addEventListener(e, o, i), () => t.removeEventListener(e, o, i)) : () => {};
    var x = (t, e) => !!t && e.includes(t);
    var M = t => t != null;
    var S = t => typeof t == "string";
    var L = t => {
        let e = t.split("-"), o = parseInt(e[e.length - 1]);
        return !isNaN(o) ? o : undefined;
    };

    // Функция для загрузки модулей
    var U = (t, e = "1", o = "iife") => {
        let r = `${t}${o === "esm" ? ".esm" : ""}.js`;
        return `https://cdn.jsdelivr.net/npm/@finsweet/attributes-${t}@${e}/${r}`;
    };

    var Ut = U(z, "1", "esm");
    var wt = `${d}-${D}`;

    // Функция для проверки поддержки
    var Z = async () => {
        var r;
        let { fsAttributes: t, location: e } = window;
        let { host: o, searchParams: i } = new URL(e.href);
        return !o.includes("webflow.io") || !i.has(wt) ? !1 : (r = t.import) == null ? void 0 : r.call(t, D, "1");
    };

    // Функции для работы с модальными окнами
    var f = `fs-${T}`;
    var ht = "modal";
    var Pt = "open";
    var vt = "close";
    var Dt = "animation";
    var Mt = "easing";
    var Lt = "duration";
    var Yt = "display";

    // Получение значений атрибутов для модальных окон
    var G = {
        element: { key: `${f}-element`, values: { modal: N(ht), open: N(Pt), close: N(vt) } },
        animation: { key: `${f}-${Dt}` },
        easing: { key: `${f}-${Mt}` },
        duration: { key: `${f}-${Lt}` },
        display: { key: `${f}-${Yt}` }
    };

    var [At, _, y] = B(G);

    var N = t => e => `${t}${e ? `-${e}` : ""}`;

    // Функции для управления анимацией
    var C = (t, { animations: e, easings: o }) => {
        let i = y(t, "animation");
        let r = x(i, Y(e)) ? e[i] : e.fade;
        let n = y(t, "duration");
        let s = y(t, "easing");
        let a = y(t, "display");
        let c = x(s, o) ? s : void 0;
        let p = n ? parseFloat(n) / 1e3 : void 0;
        return { animation: r, display: a || "flex", easing: c, duration: p };
    };

    // Управление активными элементами
    var O = t => {
        let e = window.fsAttributes[t];
        if (e) {
            let i = e.activeElements || [];
            if (i.length > 0) {
                for (let s of i) {
                    if (s instanceof Object && s.element && s.element.classList.contains("fs-modal")) {
                        s.element.classList.remove("fs-modal");
                        U("modal", "close", s);
                    }
                }
            }
        }
    };

    // Установка и запуск модальных окон
    window.fsAttributes = window.fsAttributes || {};
    window.fsAttributes.modal = window.fsAttributes.modal || {};
    window.fsAttributes.modal.activeElements = [];
    window.fsAttributes.modal.closeHandler = () => {
        let t = window.fsAttributes.modal.activeElements;
        for (let e of t) {
            e && e instanceof Object && e.element && e.element.classList.contains("fs-modal") && e.element.classList.remove("fs-modal") && U("modal", "close", e);
        }
    };
    U("modal", "start");

    window.fsAttributes.modal.openHandler = (t, e) => {
        let { open: i } = window.fsAttributes.modal;
        return i && i instanceof Function && i(t, e);
    };

    window.fsAttributes.modal.runModalClose = () => {
        let { close: t } = window.fsAttributes.modal;
        return t && t instanceof Function && t();
    };

    window.fsAttributes.modal.runModalCloseAll = () => {
        let { close: t } = window.fsAttributes.modal;
        return t && t instanceof Function && t();
    };
})();
