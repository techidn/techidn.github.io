---
title: Cara Unsubscribe Channel YouTube Sekaligus Banyak
layout: post
author: techidn
categories: Tutorial
tags: YouTube
image: assets/images/youtube_unsub.jpg
featured: false
---

Kamu adalah pecinta channel youtube dan telah mensubscribe banyak channel?. Banyaknya tayangan yang diberikan di channel youtube kerap membuatmu merasa bosan karena tidak ber variannya video. Dengan begitu tentu akan muncul keinginan untuk unsubscribe nya bukan? Jika iya, kamu dapat mengikuti beberapa cara unsubscribe youtube yang akan kami berikan. 

Untuk unsubscribe atau berhenti mengikuti channel youtube dapat dilakukan dengan cara instan. Disamping itu, cara untuk meng unsubscribe ini dapat dilakukan untuk menyeleksi setiap channel yang tidak aktif dalam mengupload video. Waktu yang digunakan untuk meng unsubscribe ini pun sangat cepat karena tidak perlu menyeleksinya satu per satu. 

## Unsubscribe Youtube Channel dengan Cara Manual 
Cara unsubscribe youtube dapat dilakukan secara manual atau satu per satu channel. Namun hal tersebut dapat dilakukan apabila channel yang diikuti masih dapat dihitung dengan jari. Jika sudah dalam jumlah yang banyak, tentu kamu akan kesulitan dalam memilahnya dan harus menggunakan cara otomatis. 

Sebelum meng unsubscribe youtube channel, pikirkan kembali dan seleksi beberapa channel penting yang tidak akan di unsubscribe. Kemudian kamu dapat menuliskan beberapa channel yang ingin di subscribe kembali di lain hari. Siapa tau, kamu ingin menonton kembali video dari channel yang telah di unsubscribe. 

1. Login pada youtube akunmu dan masuk di bagian home 
2. Klik subscriptions pada bagian kiri 
3. Pilih manage di bagian kanan atas, tepat dibawah ikon profil 
4. Kemudian akan muncul deretan channel youtube yang kamu subscribe
5. Pilih channel yang akan di unsubscribe 
6. Klik pada kolom subscribed dan akan muncul popup 
7. Klik unsubscribe 
8. Apabila masih belum yakin untuk berhenti mengikuti, kamu dapat klik cancel terlebih dahulu.

## Cara Unsubscribe Youtube Secara Massal 
Bagi kamu yang mengikuti banyak channel dan ingin berhenti mengikuti, kamu dapat melakukannya secara massal. Bahkan dalam jumlah puluhan hingga ratusan. Cara unsubscribe ini dapat dilakukan dengan waktu yang sangat singkat dalam sekejap. Ikuti langkah – langkah berikut: 

1. Masuk dan login pada situs youtube 
2. Masuk di bagian home youtube 
3. Klik subscriptions pada bagian kiri 
4. Klik manage di bagian kanan atas, di bawah ikon profil 
5. Selanjutnya akan muncul beberapa channel yang telah di subscribe 
6. Scroll sampai bawah sampai muncul jumlah channel yang diikuti pada bagian layar 
7. Klik kanan dan pilih inspect element atau inspect, pilihan tersebut tergantung pada browser yang digunakan 
8. Klik console 
9. Terakhir masukkan script dibawah ini
10. Klik enter 

### Script Unsubscribe Channel YouTube sekaligus

```js
/** 
  * Youtube bulk unsubsribe fn.
 * Wrapping this in an IIFE for browser compatibility.
  */
(async function iife() {
   // This is the time delay after which the "unsubscribe" button is "clicked"; Tweak to your liking!
  var UNSUBSCRIBE_DELAY_TIME = 2000
 
/**
  * Delay runner. Wraps `setTimeout` so it can be `await`ed on. 
 * @param {Function} fn 
  * @param {number} delay 
 */
   var runAfterDelay = (fn, delay) => new Promise((resolve, reject) => {
    setTimeout(() => {
       fn()
      resolve()
     }, delay)
  })
 

 
  // Get the channel list; this can be considered a row in the page.
   var channels = Array.from(document.getElementsByTagName(`ytd-channel-renderer`))
  console.log(`${channels.length} channels found.`)
 
  var ctr = 0
   for (const channel of channels) {
    // Get the subsribe button and trigger a "click"
     channel.querySelector(`[aria-label^='Unsubscribe from']`).click()
    await runAfterDelay(() => {
       // Get the dialog container...
      document.getElementsByTagName(`yt-confirm-dialog-renderer`)[0]
         // and find the confirm button...
        .querySelector(`#confirm-button`)
         // and "trigger" the click!
        .click()
       console.log(`Unsubsribed ${ctr + 1}/${channels.length}`)
      ctr++
     }, UNSUBSCRIBE_DELAY_TIME)
  }
 })()
youtubeUnsubscriber();
````

Itulah beberapa cara unsubscribe youtube channel yang telah kamu ikuti. Pilihlah channel – channel youtube yang bermanfaat, memberikan informasi serta tidak membosankan ditonton. Selamat mencoba! 
