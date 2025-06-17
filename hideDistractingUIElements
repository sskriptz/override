let elems = [
    "egg-breaker-wrap"
    "teamScores",
    "spatulaPlayer",
    "cts-message",
    "account_panel",
    "chatIn",
    "chatOut",
    "playerList",
    "bigMessageContainer",
    "gameMessage",
    "kill-death-box",
    "inGameUI",
    "killTicker",
    "spectate",
    "chickenBadge"
];

let hideHDUEInterval = setInterval(() => {
	if (typeof (vueApp) === "undefined") return;
	clearInterval(hideHDUEInterval);

	let oldLocFunc = vueApp.setLocData;
	vueApp.setLocData = (languageCode, newLocData) => {
		oldLocFunc(languageCode, newLocData);
		vueApp.loc.keybindings_toggle_hdue = "Toggle HDUE";
	}

	vueApp.loc.keybindings_toggle_hdue = "Toggle HDUE";
	vueApp.settingsUi.controls.keyboard.spectate.push({ id: 'toggle_hdue', locKey: 'keybindings_toggle_hdue', value: 'U' });

	document.addEventListener('keydown', (event) => {
		if (document.activeElement.tagName == "INPUT" || !extern.inGame || vueApp.game.isPaused) return;
		let hideKey2 = vueApp.settingsUi.controls.keyboard.spectate[vueApp.settingsUi.controls.keyboard.spectate.findIndex(item => item.id === "toggle_hdue")].value.toLowerCase();
		if (event.key === hideKey2) elems.map(id => document.getElementById(id)).forEach(e => e.style.opacity ^= 1);	
	});
}, 250);
