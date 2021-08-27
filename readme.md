Open the page to get the links - Use this script to get links (console)

let urls = [];
$('.homeLink').each(function(index, element){

let url = 'https://www.superteacherworksheets.com' +$(this).attr('href');
urls.push(url);

});
console.log(JSON.stringify(urls));

copy the urls and paste into links.js.
run - node .\download.js









***************************************
For Browser Console


function downloadfile(url, filename) {
fetch(url).then(function(t) {
    return t.blob().then((b)=>{
        var a = document.createElement("a");
        a.href = URL.createObjectURL(b);
        a.setAttribute("download", filename);
        a.click();
    });
  });
}

let links = [];
jQuery('.box-20 a').each(function(index, element){
let link = jQuery(this).attr('href');
console.log(link);
if(link && link !== undefined && link.length > 10){
    let url =  link;
    links.push(url);
 }

});


links.forEach(async (link) =>{
    //console.log( 'https://www.writinga-z.com' + link ,  link.replaceAll("/", "_").replaceAll('_main_', 'Emerging_Lessons_') + ".pdf");
    await downloadfile('https://www.writinga-z.com' + link ,  link.replaceAll("/", "_").replaceAll('_main_', 'Skills_Connections_') + ".pdf");
})

//downloadfile( 'https://www.writinga-z.com/main/' +   "https://www.writinga-z.com/main/Download/resource/waz/id/1301", '1301.pdf')