# Simple HAProxy config generator
Converts simple **haproxy.json** to **haproxy.cfg**. For lazy boys and girls.
Just run ```./haproxy-config.py```.

## Config JSON
Here an example of **haproxy.json**:

    {
        "auth_groups": [
            {
                "name": "home",
                "users": [{
                    "login": "jack",
                    "pass": "12345"
                }]
            },
            {
                "name": "friends",
                "users": [{
                    "login": "carl",
                    "pass": "54321"
                }]
            }
        ],
        "settings": {
            "listen_port": 80
        },
        "sites": [
            {
                "default": true,
                "name": "default_page",
                "port": 8020
            },
            {
                "host": "blog.site.com",
                "name": "blog",
                "port": 8021
            },
            {
                "auth_group": "home",
                "host": "api.site.com",
                "name": "api",
                "port": 8022,
                "realm": "MyAPI"
            },
            {
                "host": "dev-api.another.com",
                "name": "dev_api",
                "port": 8022,
                "remote": "192.168.1.3"
            }
        ]
    }

# License
The MIT License (MIT)

Copyright (c) 2016 Nikolay Volosatov

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
