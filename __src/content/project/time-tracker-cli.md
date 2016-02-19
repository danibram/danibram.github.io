+++
date = "2016-02-07T20:13:19+01:00"
description = "Super tiny and ligthway time tracker for all cli lovers."
project_url = ""
title = "time tracker cli"
version = "v1.1.2"

+++

Super tiny and ligthway time tracker for all cli lovers.

## Usage

[![asciicast](https://asciinema.org/a/dzegwhnwxvv28q84u8uvsgyas.png)](https://asciinema.org/a/dzegwhnwxvv28q84u8uvsgyas)

```
±❩❩❩ timer --help

    Usage: timer [options]

    Tiny time tracker for projects

    Options:

      -h, --help                         output usage information
      -V, --version                      output the version number
      -s, --start <task> <description>   Start the timer task.
      -f, --finish <task> <description>  Stops the timer task.
      -d, --description <description>    Adds a description for the task only in start/stop methods.
      -a, --add <task> <timeString>      Adds time to a task. Example: "1h2m3s"
      --remove <task> <timeString>       Subtract time from a task. Example: "1h2m3s"
      -l, --log <task>                   Logs the timer task.
      -r, --report <task> <rate>         Report time of the tasks, searched by key, you can report all using all as key. Also you can pass a rate to calc an amount ex: 20h, calc the hours and mulpitly by 20
      -e, --export                       Prints the json of all tasks.
```

- To start a task run:
```
$ timer -s <key of the task> -d  <description>
```
- To finish a task run:
```
$ timer -s <key of the task> -d  <description>
```
- You can add a description adding:
```
$ timer -s <key of the task> -d  <description>
$ timer -h <key of the task> -d  <description>
```
- You can also see the timer running:
```
$ timer -l <key of the task>
```
## How it works
The data are stored inside ~/.config/time-tracker-cli.json
If you open you should see:

```javascript
{
	"tasks": {
		"work1.website.design": {
			"start": "2016-02-19T10:00:36.393Z",
			"stop": "2016-02-19T18:01:50.921Z"
		},
		"work1.website.deployServer": {
			"start": "2016-02-19T10:01:59.116Z",
			"stop": "2016-02-19T10:32:10.687Z"
		},
		"work1.api.develop.userController": {
			"start": "2016-02-19T10:04:23.060Z",
			"stop": "2016-02-19T20:04:36.836Z"
		},
		"work1.api.develop.loginController": {
			"start": "2016-02-19T10:09:41.848Z",
			"stop": "2016-02-19T13:11:54.059Z"
		}
	}
}
```

The -r method, simply finds by regex and count the time.

## Development

Run ```npm install;npm run dev``` to watch the proyect, and compile the code automatically.
Run ```npm build``` to build the module.

## License
Licensed under the MIT license. 2015
