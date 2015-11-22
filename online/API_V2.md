## API Document

### License

Before GPL2

- Do not publish it as a third party api service. Please contact author before using official api service.
- Do not submit it as a binary to any form for competitions or exhibitions.

``` 
General Public License version 2 (GPLv2).

Copyright (C) 2015-2016 LNTU.ORG (https://lntu.org)
Copyright (C) 2014-2015 TakWolf <takwolf@foxmail.com>

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation; either version 2 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License along
with this program; if not, write to the Free Software Foundation, Inc.,
51 Franklin Street, Fifth Floor, Boston, MA 02110-1301 USA.
```

### Overview

This is an agent of Liaoning Technical University Education Administration System.

### Principle

This proxy just like a spider, when you request in this system, our proxy server would simulate your login, analyze the important information, and finally return json to you.

**WARMING: We don't collect your imformation, once you changed your password the proxy won't work anymore**

### Useage

- Our API obey RESTful Standard strictly
- We use SSL to make it more security

#### ROOT URL

`https://api.online.lntu.org/`

#### Login

- Method: POST
- URI: account/login


- param

| param name | not null | type   | remarks |
| ---------- | -------- | ------ | ------- |
| userId     | yes      | string |         |
| password   | yes      | string |         |

- return:

| param name | type     | remarks                           |
| ---------- | -------- | --------------------------------- |
| userId     | string   |                                   |
| loginToken | string   | save it safely, will be used next |
| expiresAt  | datetime | ISO 8601 format                   |
| userType   | string   | STUDENT / ADMIN / TEACHER         |

- error: Test it on your own

#### Self Imformation

- Header: Key: "Authorization", Value: loginToken
- Method: GET
- URI: student/~self
- param: nil
- return: [Try it on your own]()
- error: Test it on your own

#### Class Table

- Header: Key: "Authorization", Value: loginToken
- Method: GET
- URI: class-table/~self
- param:

| param name | not null | type   | remarks               |
| ---------- | -------- | ------ | --------------------- |
| year       | yes      | string | 2014 / 2015 and so on |
| term       | yes      | string | 春 / 秋                 |

- return: [Try it on your own](#)
- error: Test it on your own

#### Unpass Course

- Header: Key: "Authorization", Value: loginToken
- Method: GET
- URI: unpass-course/~self
- param: nil
- return: [Try it on your own](#)
- error: Test it on your own

#### Grades

- Header: Key: "Authorization", Value: loginToken
- Method: GET
- URI: grades/~self
- param: nil
- return: [Try it on your own](#)
- error: Test it on your own
- remarks: Includes your average credit

#### Exam Plan

- Header: Key: "Authorization", Value: loginToken
- Method: GET
- URI: exam-plan/~self
- param: nil
- return: [Try it on your own](#)
- error: Test it on your own

#### Skill Test Score

- Header: Key: "Authorization", Value: loginToken
- Method: GET
- URI: skill-test-score/~self
- param: nil
- return: [Try it on your own](#)
- error: Test it on your own
