const body = document.querySelector('body');
const services = document.querySelector('.header-link');
const headerNavButton = document.querySelector('.header__nav-button');
const menu1 = document.querySelector('.header__menu1');
const menu1Button = Array.from(menu1.querySelectorAll('.header__menu-button'));
const menu1TextAll = Array.from(menu1.querySelectorAll('.header__menu-text'));
const menu2 = Array.from(document.querySelectorAll('.header__menu2'));
const menu2Wrapper = document.querySelector('.header__menu2-wrapper')
const menu2Button = Array.from(menu2Wrapper.querySelectorAll('.header__menu-button'));
const menu2TextAll = Array.from(menu2Wrapper.querySelectorAll('.header__menu-text'));
const menu3 = Array.from(document.querySelectorAll('.header__menu3'));
const dataMenu3 =Array.from(document.querySelectorAll('[data-menu3]'));
const locationButton1 = document.querySelector('.header__location-button1');
const locationButton2 = document.querySelector('.header__location-button2');
const headerLocation = document.querySelector('.header__connection');
const locationIssue = document.querySelector('.header__location-issue');
const locationDetermination = document.querySelector('.location-determination');
const allCities = Array.from(document.querySelectorAll('.location-determination__item-text'));
let cityAdd = document.querySelector('.header__connection-city');
let cityAdd1 = document.querySelector('.header__location-text .city');
const main = document.querySelector('main');
//__________________________________
//МЕНЮ:
services.addEventListener('click', function(e){
headerNavButton.classList.toggle('active');
services.classList.toggle('active');
menu1.classList.toggle('active');
body.classList.toggle('modal-open');
main.classList.toggle('opasiti');

for(let j = 0; j < menu2.length; j++ ){
menu2[j].classList.remove('active');	
}
removeMenu3();
menuButtonColorRemove();
menu1TextColorRemove();
});

menu1.addEventListener('click', event => {
removeMenu3();
menu1TextColorRemove()
menu2TextColorRemove();

	for(let j = 0; j < menu2Button.length; j++){
		menu2Button[j].classList.remove('active');
	}

	 if (event.target.className == 'header__menu-button'){
	for(let i = 0; i < menu1Button.length; i++){
       if (menu1Button[i] === event.target){
       	menu1Button[i].classList.toggle('active');
       	menu1Button[i].previousElementSibling.classList.add('active');
       //открываем соответствующее menu2:
       	for(let j = 0; j < menu2.length; j++ ){
       		if(j === i){
       			
       			menu2[j].classList.toggle('active');
       		}
       		if(j !== i){
       			menu2[j].classList.remove('active');
       		}
       	}
       }else if(menu1Button[i] !== event.target){
       		menu1Button[i].classList.remove('active');
       }
	 }
	}
})
//переход со 2 меню на 3:
document.addEventListener('click', event => {
	 if (event.target.className == 'header__menu-button'){
	    
	 	let men = event.target.closest('.header__menu-item');
	if(men){
	menu2TextColorRemove()
	//цвет кнопок:
	  for(let j = 0; j < menu2Button.length; j++){
	 if (menu2Button[j] === event.target){
       	menu2Button[j].classList.toggle('active');
        let menu2Text = menu2Button[j].previousElementSibling;
        menu2Text.classList.add('active');

       } else {menu2Button[j].classList.remove('active');}
	}

	 	let dataMenu = men.getAttribute('data-menu');
	 	 	
	   let headerLinks = document.querySelector(`[data-menu3= "${dataMenu}"]`);
	   let topp = men.getBoundingClientRect().top ;
     
       headerLinks.classList.toggle('active');
       headerLinks.style.top = `${topp}px`
        let symbol = dataMenu - 1 ;
      
       for(let k = 0; k < dataMenu3.length; k++){
       	if(k !== symbol){
       		
       		dataMenu3[k].classList.remove('active');


       	}
    }
}
	}
})

function removeMenu3(){
	for(let k = 0; k < dataMenu3.length; k++){
	dataMenu3[k].classList.remove('active');
	}
}
function menuButtonColorRemove(){
    for(let i = 0; i < menu1Button.length; i++){
        menu1Button[i].classList.remove('active');
    }

	for(let j = 0; j < menu2Button.length; j++){
		menu2Button[j].classList.remove('active');
	}
}
function menu1TextColorRemove(){
   		for(let k = 0; k < menu1TextAll.length; k++){
		menu1TextAll[k].classList.remove('active');
	}
}
function menu2TextColorRemove(){
   		for(let k = 0; k < menu2TextAll.length; k++){
		menu2TextAll[k].classList.remove('active');
	}
}
//__________________________________________


//------location---------------
headerLocation.addEventListener('click',function(){
locationIssue.classList.remove('none');
});
locationButton1.addEventListener('click',function(){
locationIssue.classList.add('none');
	locationDetermination.classList.add('transform');
	setTimeout(transformAdd, 300);
	body.classList.remove('location-hidden');
});
locationButton2.addEventListener('click',function(){
locationDetermination.classList.remove('none');
setTimeout(transformRemove, 300);
body.classList.add('location-hidden');
locationIssue.classList.add('none');
});
function transformRemove (){
locationDetermination.classList.remove('transform');	
}
function transformAdd(){
locationDetermination.classList.add('none');	
}
locationDetermination.addEventListener('click',function(e){

for(let i = 0; i < allCities.length; i++){
	if(allCities[i] === e.target){
		let city = e.target.textContent;
		cityAdd.textContent = city;
		cityAdd1.textContent = city;
		locationDetermination.classList.add('transform');
		setTimeout(transformAdd, 300);
	    body.classList.remove('location-hidden');
	    locationIssue.classList.add('none');
	}
}

});
/*----------------Навигация-------------------*/

const mainItems = document.querySelectorAll('.header__nav-item');
const mainBtn = document.querySelector('.main__btn');

for (let item of mainItems) {
    item.addEventListener('click', function() {
        const title = document.querySelector('#' + item.dataset.goto);
        let indent = 200 ;
        const gotoBlockValue = title.getBoundingClientRect().top + scrollY - indent;

        window.scrollTo({
            top: gotoBlockValue,
            left: 0,
            behavior: "smooth"
        });
    });
}

document.addEventListener('scroll', function() {
    if (scrollY >= 1163) {
        mainBtn.classList.remove('hidden');
    } else {
        mainBtn.classList.add('hidden');
    }
});

mainBtn.addEventListener('click', function() {
    window.scrollTo({
        top: 0,
        left: 0,
        behavior: "smooth"
    });
});

/*-------------Аккордион---------------*/
let titles = Array.from(document.querySelectorAll('.accordion__title'));

for (let title of titles) {
    title.addEventListener('click', () =>{
        title.nextElementSibling.classList.toggle('hiddens')
    })
}
/*-------------------------------------*/
