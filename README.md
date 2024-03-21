## Telehack

    Telehack is a simulation of a stylized arpanet/usenet, circa 1985-1990.
    It is a full multi-user simulation, including 26,600+ simulated hosts
    from the early net, thousands of files from the era, a collection of
    adventure and IF games, a working BASIC interpreter with a library of
    programs to run, simulated historical users, and more.

## Connecting

On the web: https://telehack.com/

Telehack supports the telnet protocol on ports 23, 1337, 8080, and 31173. Open a shell and type:

    telnet telehack.com

Telehack also supports the secure shell (SSH) protocol on port 2222:

    ssh -p 2222 guest@telehack.com

HTTPS and SSH provide encryption, but telnet provides no encryption. After creating a username, you can connect via SSH with your username instead of guest. Also, you can optionally add a public key with the `SET KEY` command.

## About this Document

Telehack is case-insensitive. Commands are often shown in uppercase to distinguish them from surrounding text. Note that you do not need to type commands in all-caps. For example:

    Type DIR for a list of files

You may type DIR or dir to obtain a list of files.

In help messages, \<\> signifies required arguments to commands, whereas \[\] signifies optional arguments. The pipe symbol \| signifies "or" or an alternative. For example:

## Getting Help

You can type ? at any prompt to get a list of available commands:

    @ ?
    Command, one of the following:
      2048        ?           a2          ac          advent      aquarium
      basic       bf          c8          cal         calc        ching
      clear       clock       cowsay      date        ddate       echo
      eliza       factor      figlet      finger      fnord       geoip
      help        ipaddr      joke        login       mac         md5
      morse       newuser     notes       octopus     phoon       pig
      ping        pong        primes      privacy     qr          rain
      rand        rfc         rig         roll        rot13       sleep
      starwars    traceroute  typespeed   units       uptime      usenet
      users       uumap       uupath      uuplot      weather     when
      zc          zork        zrun

The HELP command provides one-line descriptions of command functions, including any modifier arguments that may be available. Examples:

    @ help
    @ help telnet
    @ help ftp

## Getting Unstuck

Any command may be terminated by typing \^C (control-C). To log out of a remote host or exit a subshell, type \^D (control-D), EXIT or QUIT.

## Quick Fun

Type `STARWARS` to view the pinnacle of ASCII-mation, a full-length
rendition of Star Wars in ASCII.

Typing `JOKE` will display a joke randomly selected from a massive unified historical arpanet/caltech joke database.

Type Aquarium to watch an animated aquarium in ASCII art.

## NLI Lobby

When you first connect to Telehack, you will be in the not-logged-in lobby. The NLI lobby is indicated by the '.' prompt:

    $ telnet telehack.com Trying 64.13.147.30...  Connected
    to telehack.com.  Escape character is '^]'.

    Connected to TELEHACK port 13

    It is 8:16 am on Saturday, April 30, 2011 in Mountain View, California, USA.
    There are 10 local users. There are 24139 hosts on the network.

      Type ? for a command list.
      Type HELP for a more detailed command listing.
      Press control-C to interrupt any command.

    May the command line live forever.

    Command, one of the following:
      2048        ?           a2          ac          advent      aquarium
      basic       bf          c8          cal         calc        ching
      clear       clock       cowsay      date        ddate       echo
      eliza       factor      figlet      finger      fnord       geoip
      help        ipaddr      joke        login       mac         md5
      morse       newuser     notes       octopus     phoon       pig
      ping        pong        primes      privacy     qr          rain
      rand        rfc         rig         roll        rot13       sleep
      starwars    traceroute  typespeed   units       uptime      usenet
      users       uumap       uupath      uuplot      weather     when
      zc          zork        zrun
    .

A limited subset of commands are available in the lobby.

To login or create a new account, type LOGIN.

## Network Hosts

There are approximately 26,600 virtual hosts on the Telehack network. These represent systems that were on the early Usenet/arpanet as well as defunct BBS systems from the 80's and 90's.

Type HOSTS to see a partial list of network hosts. Type HELP HOSTS for more information on the hosts command.

A collection of retro files has been distributed across the hosts in the network. The files were sourced from the extensive archive assembled by Jason Scott of Textfiles.com as well as other sources.

## Telnetting to Hosts

You may telnet to any host appearing in your netstat list:

    @ netstat
       host      organization                               location
       ----      ------------                               --------
       sunkist   Sun Microsystems Inc.                      Irvine, California
     ! mimsy     Computer Science Dept., Univ of Maryland   College Park, MD
       spgh01    Church of the Holy Sepulchre               Butler, PA
     * vitam6    Vitalink Communications                    Fremont, CA
       hell      Clinton Reilly Campaigns                   Alameda, CA
       accom     Axial Corp.                                Belmont, CA

    @ telnet mimsy
    Trying...
    Connected to MIMSY

    Computer Science Dept., University of Maryland, College Park
    DEC Vax-8600 4.3BSD

    login: guest

    Authentication successful.
    Last login: Thu May 5 16:32:51 2011

       WARNING:  You must have prior authorization to access this system.
                 All connections are logged and monitored. By connecting to
                 to this system you fully consent to all monitoring.
                 Unauthorized access or use will be prosecuted to the full
                 extent of the law.


    mimsy$

If you have not yet hacked into a host, you can try to login as the guest user. The full set of commands on the host may not be available if you are logged in as guest.

The \* symbol in the netstat output denotes that you have a login account on that host, and the ! symbol denotes that you have root there. These symbols also appear in the output of other commands, such as uuplot.

## Dialing a host

You may connect to a host by using the DIAL command.

    @dial 3148372840

dialing ATDT (314) 837-2840 CONNECT 9600

Connected to THEOASIS

## BASIC Interpreter

To enter the basic interpreter, type BASIC.

    @ basic
    Dartmouth DTSS TeleBASIC (c) 1964,1966,1969,1970,1971,1979

The basic interpreter subsystem has a number of historical programs compiled from the SIMTEL archives as well as other sources. To see a full list of available programs, type DIR within basic. You can load a program with LOAD or begin execution with RUN.

Basic commands are:

    > help
    delete                   delete a user program
    dir                      directory of basic programs
    help                     print this list
    list                     list the program in memory
    load <file>              load program from file
    quit                     exit the basic interpreter
    renumber [start[,inc]]   renumber the program in memory
    run                      run the program in memory
    run <program>            load and run the specified program file
    save <file>              save a user program

Example basic session:

    @ basic
    Dartmouth DTSS TeleBASIC (c) 1964,1966,1969,1970,1971,1979
    > ?
    Command, one of the following:
      delete  dir     help    list    load    quit    run     renumber
      save
    > dir
      23matches.bas    3dplot.bas       aceyducey.bas    aceyducy.bas
      astrnmy2.bas     bar.bas          basketball.bas   basketbl.bas
      batnum.bas       baz.bas          bigcal2.bas      birthday.bas
      bobo.bas         bombsaway.bas    bombsawy.bas     boxing.bas
      budget.bas       bug.bas          bunny.bas        buzzword.bas
      calendar.bas     calendr5.bas     change.bas       chemist.bas
      chief.bas        combat.bas       command.bas      cpmprt51.bas
      craps.bas        cube.bas         deedyork.bas     delers.bas
      depthcharge.bas  depthchg.bas     diamond.bas      eddie.bas
      euphoria.bas     evenwin1.bas     evenwins.bas     fakephre.bas
      feesten.bas      finance.bas      godd.bas         gomoko.bas
      gunner.bas       hammurabi.bas    hamurabi.bas     hello.bas
      hi-lo.bas        hilo.bas         hurkle.bas       ic-timer.bas
      kalfeest.bas     kinema.bas       lander.bas       lem.bas
      letter.bas       life.bas         lifscore.bas     litquiz.bas
      loan2.bas        log10k.bas       lunar.bas        maptest.bas
      massa.bas        mathdice.bas     million.bas      nicoma.bas
      nicomachus.bas   nim.bas          number.bas       orbit.bas
      pirate.bas       pizza.bas        poetry.bas       qubit.bas
      queen.bas        rc5.bas          rocket.bas       rockscissor.bas
      rocksp.bas       rusrou.bas       satelite.bas     sceptre1.bas
      slalom.bas       slots.bas        snafufun.bas     sort.bas
      splat.bas        stars.bas        stock.bas        stockmarket.bas
      survival2.bas    target.bas       tem-ins.bas      test1.bas
      tictac1.bas      tictactoe1.bas   timer555.bas     trap.bas
      ttl-scrl.bas     ucase.bas        uitleg1.bas      uitleg2.bas
      unprotct.bas     war.bas          weekday.bas      windchil.bas
      xfertime.bas     xformer.bas      ykw1.bas         ykw2.bas
    > load hello.bas
    Ok
    > list
        2  PRINT TAB(33); HELLO
        4  PRINT TAB(15); CREATIVE COMPUTING  MORRISTOWN, NEW JERSEY
        6  PRINT: PRINT: PRINT
       10  PRINT  HELLO.  MY NAME IS CREATIVE COMPUTER.
       20  PRINT: PRINT: INPUT  WHAT'S YOUR NAME ;N$: PRINT
       30  PRINT  HI THERE,  ;N$; , ARE YOU ENJOYING YOURSELF HERE ;
       40  INPUT B$: PRINT
       50  IF B$= YES  THEN 70
       55  IF B$= NO  THEN 80
    ...
    > run
    CREATIVE COMPUTING  MORRISTOWN, NEW JERSEY

    HELLO.  MY NAME IS CREATIVE COMPUTER.

    WHAT'S YOUR NAME?

## Remote Terminal Monitoring

The link command will connect a remote user's tty to your tty. This will let you assist the remote user by being able to view the remote output.

    @ link <user or port>

In this case, the other user would see something like

    .
    %link from port 16 user forbin

And their session from that point would be mirrored on the linking user's terminal.

There is also a separate facility within ptycon to allow simultaneous monitoring of all connected ports.

## Finger from Outside

Telehack also responds to finger requests from the outside Internet on port 79:

    $ finger @telehack.com
    TELEHACK SYSTEM STATUS  04-May-11  23:27:08
    4 users

      port  username   status               last  what     where
      ----  --------   ------               ----  ----     -----
      0     operator   System Operator      5m             console
      16    -                               3m    alice3   Lithuania
      17    forbin     Dr. Charles Forbin   13m            Provo, UT
      20    foo        Yoda Soda            19m   ptycon   Oakland, CA

    $ finger forbin@telehack.com
    USER: forbin
       system level:          WIZARD
       account age:           95 days
       last login:            today
       system connects:       5
       commands executed:     143

       user status bits:
         HACK10      Hacked 10 network hosts          30-Jan-11  23:19:57
         HACK5       Hacked 5 network hosts           30-Jan-11  21:00:34
         HACKER      Hack the Planet                  29-Jan-11  22:31:48
         ACCT        Registered User                  29-Jan-11  22:23:17

## How to enable telnet in Windows 7, 10, and 11

Windows 7, 10 and 11 ship with a telnet client, but it is shut off by default. To enable it, do the following:

    Start
    Control Panel
    Programs And Features
    Turn Windows features on or off
    Check Telnet Client
    Hit OK

After that, you can open a command prompt and type

    telnet telehack.com
