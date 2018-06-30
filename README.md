# hl
hl - highlights anything that matches your REGEX, in the COLOUR desired - cuz sometimes 'grep' isn't enough

## Authors

* **Chris Phillips** - *Initial work* - [furriephillips](https://github.com/furriephillips)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under The Artistic License 2.0 - see the [LICENSE](LICENSE) file for details

## Example

```shell
% hl

You have to at least define the pattern you want to be highlighted
 and optionally, a colour for the highlighting.

Usage: hl <PATTERN> [HLCOLOUR]

Currently supported colours: -

 red (default if none specified)
 green
 yellow
 blue
 pink
 lightblue
 grey

The colours are subject to interpretation!

You can string a few hl/highlight commands together, in order to highlight
 various elements...  Like this: -

# tail -f /var/log/maillog | hl NOQUEUE lightblue | hl 'blocked using sbl-xbl.spamhaus.org' pink | hl warning red
```

## Real example, highlighting spammers in a maillog

```
# tail -F /var/log/maillog | hl NOQUEUE lightblue | hl 'blocked using zen.spamhaus.org' pink | hl warning red | head       
May  6 08:51:05 remote postfix/smtpd[27085]: warning: hostname residencial-200.6.178.132.costanet.com.co does not resolve to address 200.6.178.132: Name or service not known
May  6 09:00:37 remote postfix/smtpd[27309]: warning: hostname mx-ll-110.164.162-91.static.3bb.co.th does not resolve to address 110.164.162.91: Name or service not known
May  6 09:00:38 remote postfix/smtpd[27309]: NOQUEUE: reject: RCPT from unknown[110.164.162.91]: 454 4.7.1 Service unavailable; Client host [110.164.162.91] blocked using zen.spamhaus.org; from=<xjpxghmbo@headlineplus.com> to=<agpie@insomniac.me.uk> proto=ESMTP helo=<mx-ll-110.164.162-91.static.3bb.co.th>
May  6 09:02:13 remote postfix/smtpd[27309]: NOQUEUE: reject: RCPT from mail182.atl171.mcdlv.net[198.2.138.182]: 450 4.2.0 <masterclass@furrie.net>: Recipient address rejected: Greylisted for 5 seconds; from=<bounce-mc.us10_40045777.393881-masterclass=furrie.net@mail182.atl171.mcdlv.net> to=<masterclass@furrie.net> proto=ESMTP helo=<mail182.atl171.mcdlv.net>
May  6 09:05:14 remote postfix/smtpd[27429]: NOQUEUE: reject: RCPT from mail209.atl81.rsgsv.net[198.2.129.209]: 450 4.2.0 <dee@furrie.net>: Recipient address rejected: Greylisted for 5 seconds; from=<bounce-mc.us9_36270041.733397-dee=furrie.net@mail209.atl81.rsgsv.net> to=<dee@furrie.net> proto=ESMTP helo=<mail209.atl81.rsgsv.net>
May  6 09:11:08 remote postfix/smtpd[27540]: warning: hostname mail.whbbrasil.com.br does not resolve to address 200.150.79.84
May  6 09:40:49 remote postfix/smtpd[28248]: warning: hostname s198-53-60-171.transpeace.com does not resolve to address 198.53.60.171: Name or service not known
May  6 10:00:31 remote postfix/smtpd[28691]: warning: hostname pc20116218266.optele.net does not resolve to address 201.162.182.66: Name or service not known
May  6 10:59:43 remote postfix/smtpd[30081]: warning: hostname static.vnpt.vn does not resolve to address 113.171.23.47
May  6 11:15:50 remote postfix/smtpd[30504]: warning: hostname static.vnpt.vn does not resolve to address 113.173.97.188
```
