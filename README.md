# file_size_url

<p align="center">
  <img align="center" src = "https://profile-counter.glitch.me/file_size_url/count.svg"> <br><br>

</p>

Get file size from URL without downloading it.
0 dependencies.  
  
Returns Promise<Number> with 'B', 'KB', 'MB', 'GB', 'TB' on success.


```bash
npm i file_size_url

```


```js

import file_size_url from 'file_size_url';

file_size_url("https://server10.mp3quran.net/bader/Rewayat-Hafs-A-n-Assem/001.mp3")
    .then(console.log) // 968.27 KB
    .catch(console.error);

```


OR 


```js

import file_size_url from 'file_size_url';

let size = await file_size_url("https://serverjyy10.mp3quran.net/bader/Rewayat-Hafs-A-n-Assem/0001.mp3")
    .catch((error) => console.log(error))

console.log(size) // 968.27 KB


```
Example for lop

```js

let array = [

    'https://server10.mp3quran.net/bader/Rewayat-Hafs-A-n-Assem/001.mp3',
    'https://server10.mp3quran.net/bader/Rewayat-Hafs-A-n-Assem/002.mp3',
    'https://server10.mp3quran.net/bader/Rewayat-Hafs-A-n-Assem/003.mp3',
    'https://server10.mp3quran.net/bader/Rewayat-Hafs-A-n-Assem/055.mp3',
    'https://server10.mp3quran.net/bader/Rewayat-Hafs-A-n-Assem/110.mp3',

]

for (let index = 0; index < array.length; index++) {

    try {

        let fies_size = await file_size_url(array[index])

        if (fies_size.toString().split('.')[0] <= 95 && fies_size.toString().split(' ')[1] === 'MB') {

            console.log(fies_size + ' || <= 95 MB');

        }

        else if (fies_size.toString().split('.')[0] > 95 && fies_size.toString().split(' ')[1] === 'MB') {

            console.log(fies_size + ' || > 95 MB');

        }

        else if (fies_size.toString().split(' ')[1] === 'KB') {

            console.log(fies_size + ' || KB');

        }


    } catch (error) {

        console.log(error);

    }

}


/* output 
968.27 KB || KB
170.58 MB || > 95 MB
95.77 MB || <= 95 MB
12.21 MB || <= 95 MB
711.92 KB || KB
*/


```

