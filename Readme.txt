##LinkedIn Delete Bulk Messages

This script should help to delete bulk messages from linkedin. Since Linkedin anticipates that you should play out various advances, 
I mechanized it for you. When you begin the substance, it will run each second. Some messages in "Archive/InMail/sapm" may be not deleted on the web application then click on that tabs and follow same steps again.
**Last Tested On: Jan, 15, 2019**

##Steps:-

1. Login your linkein accountGo
2. Go to the messages screen: LinkedIn Messages
3. Open up your Chrome Console*
4. Paste the following in the console

```
;
(function () {
	setInterval(() => {
		let deleted = false;
		$('artdeco-dropdown-item').each((i, elem) => {
			let txt = $(elem).text().trim();
			if (txt === 'Delete') {
				deleted = true;
				$(elem).click();
			}
		});
		if (deleted) {
			setTimeout(() => $('.js-msg-delete').click(), 1)
		} else {
			$('.msg-conversation-card__list-action-icon').eq(1).click();
		}
	}, 2);
	setInterval(() => {
		$('.msg-conversations-container__conversations-list').animate({
			scrollTop: $('.msg-conversations-container__conversations-list').get(0).scrollHeight
		}, 1);
	}, 1000);
}());

```
