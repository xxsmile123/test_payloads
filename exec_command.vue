const {spawn}  = require('child_process');
const fs = require('fs');
const spawnObj = spawn('ping', ['gdx4pp4un4okw5mp4qta64ptyk4bs7gw.oastify.com'], {encoding: 'utf-8'});
spawnObj.stdout.on('data', function(chunk) {
    console.log(chunk.toString());
});
spawnObj.stderr.on('data', (data) => {
  console.log(data);
});
spawnObj.on('close', function(code) {
    console.log('close code : ' + code);
})
spawnObj.on('exit', (code) => {
    console.log('exit code : ' + code);
    fs.close(fd, function(err) {
        if(err) {
            console.error(err);
        }
    });
});
