---
layout: page
permalink: /contact/
---

<style>
  input[type=text] {
    width: 300px; /*가로크기*/
    height: 50px; /*세로크기*/
    background-color: #fafafa; /*배경색*/
    border:2.0px solid #000000; /*테두리 두께, 선스타일, 색상*/
    border-radius:4px; /*테두리 둥글게*/
    outline:none; /*기본테두리안보이게*/
    padding:3px 3px 2px 7px; /*안쪽여백*/
    box-sizing:border-box; /*테두리를 기준으로 박스크기 설정*/
    transition:.3s; /*서서히 나타내기*/
    font-family: Courier;
  }

  /*포커스 되었을 때*/
  input[type=text]:focus{
    width: 60%;
    border:2px solid #4285f4;
    box-shadow:0 0 8px 0 #4285f4;
    background-color: #ffffff;
    color: blue; /*글자색*/
    font-family: Courier;
  }

  textarea[type=message] {
    width: 300px; /*가로크기*/
    height: 300px; /*세로크기*/
    background-color: #fafafa; /*배경색*/
    border:2px solid #000000; /*테두리 두께, 선스타일, 색상*/
    border-radius:4px; /*테두리 둥글게*/
    outline:none; /*기본테두리안보이게*/
    padding:3px 3px 2px 7px; /*안쪽여백*/
    box-sizing:border-box; /*테두리를 기준으로 박스크기 설정*/
    transition:.3s; /*서서히 나타내기*/
    font-family: Courier;
    resize: none;
  }

  /*포커스 되었을 때*/
  textarea[type=message]:focus{
    width: 70%;
    border:2px solid #4285f4;
    box-shadow:0 0 8px 0 #4285f4;
    background-color: #ffffff;
    color: blue; /*글자색*/
    font-family: Courier;
</style>

<div align="center">
  <p>
    <span style="font-size: xx-large; font-weight: 900; border-bottom: 12px solid #dcf1fb; padding: 0 0 0 0.2em;">
      Contact Me!
    </span>
  </p>

  <br>
  <form
    action="https://formspree.io/f/xnqwdayg"
    method="POST"
  >
    <fieldset id="fs-frm-inputs" style="border:0; background:Plum;">
      <label>
        Your email
        <br>
        <input type="text" name="email" placeholder="Email">
      </label>
      <br>
      <br>
      <label>
        Your full name
        <br>
        <input type="text" name="name" placeholder="Full Name">
      </label>
      <br>
      <br>
      <label>
        Your message
        <br>
        <textarea type="message" name="message" placeholder="Message"></textarea>
      </label>
      <br>
      <br>
      <button id="send" type="submit" style="color: #fff; background:RoyalBlue; font-size:2em; border-radius:0.5em; padding:5px 20px;">
        <span>
          Submit
        </span>
      </button>
    </fieldset>
  </form>
</div>