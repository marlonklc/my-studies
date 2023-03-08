## commom commands
##### show service status: `systemctl status <servicename>`
##### find any file wich contains a text: `find ./* -type f -exec grep -l <textToFind> {} \;`

#### fix problem with 'unexpeted end of file' or '$'\r': command not found' (problem edit linux files using windows via terminal) 
`sed -i 's/\r$//' filename`
