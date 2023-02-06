#!/bin/bash
clear
#--------[ DESENVOLVIDO POR @MSCPERU ]-----------#
source ShellBot.sh
touch lista
[[ -z $1 ]] && {
    clear && echo "INFORME EL TOKEN" && return 0
}
# Informações Server 2
ip_server2="SU-IP-AQUI"
senha_server2="SU-PAS"
# Informações Server 3
ip_server3="SU-IP-AQUI"
senha_server3="SU-PASS-AQUI"
[[ ! -e RESET ]] && touch RESET
api_bot=$1
ShellBot.init --token "$api_bot" --monitor --flush
ShellBot.username

# - Funcao menu
menu() {
    local msg
        msg="=×=×=×=×=×=×=×=×=×=×=×=×=×=\n"
        msg+="<b>•••••• HOLA BIENVENIDO •••••</b>\n"
        msg+="=×=×=×=×=×=×=×=×=×=×=×=×=×=\n\n"
        msg+="<b>GENERE SU CUENTA GRATIS!</b>"
        ShellBot.sendMessage --chat_id ${message_chat_id[$id]} \
        --text "$(echo -e $msg)" \
        --reply_markup "$keyboard1" \
        --parse_mode html
        return 0
}

# - funcao criar ssh
criarteste() {
    [[ $(grep -wc ${callback_query_from_id} lista) != '0' ]] && {
      ShellBot.sendMessage --chat_id ${callback_query_message_chat_id} \
         --text "YA CREASTE TU CUENTA\nINTENTA MAÑANA!"
      return 0
    }
    usuario=$(echo GRATIS$(( RANDOM% + 2500 )))
    senha='12345h'
    limite='2'
    tempo='500'
    tuserdate=$(date '+%C%y/%m/%d' -d " +3 days")
    useradd -M -N -s /bin/false $usuario -e $tuserdate > /dev/null 2>&1
    (echo "$senha";echo "$senha") | passwd $usuario > /dev/null 2>&1
    echo "$senha" > /etc/SSHPlus/senha/$usuario
    echo "$usuario $limite" >> /root/usuarios.db
    echo "#!/bin/bash
pkill -f "$usuario"
userdel --force $usuario
grep -v ^$usuario[[:space:]] /root/usuarios.db > /tmp/ph ; cat /tmp/ph > /root/usuarios.db
rm /etc/SSHPlus/senha/$usuario > /dev/null 2>&1
rm -rf /etc/SSHPlus/userteste/$usuario.sh" > /etc/SSHPlus/userteste/$usuario.sh
    chmod +x /etc/SSHPlus/userteste/$usuario.sh
    at -f /etc/SSHPlus/userteste/$usuario.sh now + $tempo min > /dev/null 2>&1
    echo ${callback_query_from_id} >> lista
    # - ENVIA O SSH
    ShellBot.sendMessage --chat_id ${callback_query_message_chat_id} \
    --text "$(echo -e " <b> CREADO CON ÉXITO </b> \n\nUSUARIO: <code>$usuario</code>\nContraseña: <code>$senha</code>\n\n⏳ Expira : EN 2 DÍAS\n\nCOMPRA TU PREMIUM DE 30 DIAS")" \
    --parse_mode html
    return 0
}

# - funcao criar ssh 2
criarteste2() {
   [[ $(grep -wc ${callback_query_from_id} lista) != '0' ]] && {
      ShellBot.sendMessage --chat_id ${callback_query_message_chat_id} \
        --text "YA CREASTE TU CUENTA\nINTENTA MAÑANA!"
      return 0
    }
    usuario=$(echo GDF$(( RANDOM% + 250 )))
    senha='12345h'
    limite='2'
    tempo=''500"
    tuserdate=$(date '+%C%y/%m/%d' -d " +2 days")
    if sshpass -p "$senha_server2" ssh -o ConnectTimeout=2 -o StrictHostKeyChecking=no root@$ip_server2 echo "ok" 1>/dev/null 2>/dev/null; then
		sshpass -p "$senha_server2" ssh -o ConnectTimeout=2 -o StrictHostKeyChecking=no root@$ip_server2 << EOF
		useradd -M -N -s /bin/false $usuario -e $tuserdate > /dev/null 2>&1
    (echo "$senha";echo "$senha") | passwd $usuario > /dev/null 2>&1
    echo "$senha" > /etc/SSHPlus/senha/$usuario
    echo "$usuario $limite" >> /root/usuarios.db
    echo "#!/bin/bash
pkill -f "$usuario"
userdel --force $usuario
grep -v ^$usuario[[:space:]] /root/usuarios.db > /tmp/ph ; cat /tmp/ph > /root/usuarios.db
rm /etc/SSHPlus/senha/$usuario > /dev/null 2>&1
rm -rf /etc/SSHPlus/userteste/$usuario.sh" > /etc/SSHPlus/userteste/$usuario.sh
chmod +x /etc/SSHPlus/userteste/$usuario.sh
at -f /etc/SSHPlus/userteste/$usuario.sh now + $tempo hour > /dev/null 2>&1
EOF
	echo ${callback_query_from_id} >> lista
    # - ENVIA O SSH
    ShellBot.sendMessage --chat_id ${callback_query_message_chat_id} \
     --text "$(echo -e " <b>CREADO CON ÉXITO</b> \n\nIP: $ip_server2\nUSUARIO: <code>$usuario</code>\nCONTRASEÑA: <code>$senha</code>\n\n⏳ Expira en: $tempo Hora")" \
    --parse_mode html
    return 0
else
ShellBot.sendMessage --chat_id ${callback_query_message_chat_id} \
	--text "$(echo -e SERVIDOR INDISPONIBLE)" \
	--parse_mode html
	return 0
fi
}

# - funcao criar ssh 3
criarteste3() {
	[[ $(grep -wc ${callback_query_from_id} lista) != '0' ]] && {
      ShellBot.sendMessage --chat_id ${callback_query_message_chat_id} \
       --text "YA CREASTE TU CUENTA\nINTENTA MAÑANA!"
      return 0
    }
    usuario=$(echo GDF$(( RANDOM% + 250 )))
    senha='1234'
    limite='2'
    tempo='24'
    tuserdate=$(date '+%C%y/%m/%d' -d " +2 days")
    if sshpass -p "$senha_server3" ssh -o ConnectTimeout=2 -o StrictHostKeyChecking=no root@$ip_server3 echo "ok" 1>/dev/null 2>/dev/null; then
		sshpass -p "$senha_server3" ssh -o ConnectTimeout=2 -o StrictHostKeyChecking=no root@$ip_server3 << EOF
		useradd -M -N -s /bin/false $usuario -e $tuserdate > /dev/null 2>&1
    (echo "$senha";echo "$senha") | passwd $usuario > /dev/null 2>&1
    echo "$senha" > /etc/SSHPlus/senha/$usuario
    echo "$usuario $limite" >> /root/usuarios.db
    echo "#!/bin/bash
pkill -f "$usuario"
userdel --force $usuario
grep -v ^$usuario[[:space:]] /root/usuarios.db > /tmp/ph ; cat /tmp/ph > /root/usuarios.db
rm /etc/SSHPlus/senha/$usuario > /dev/null 2>&1
rm -rf /etc/SSHPlus/userteste/$usuario.sh" > /etc/SSHPlus/userteste/$usuario.sh
chmod +x /etc/SSHPlus/userteste/$usuario.sh
at -f /etc/SSHPlus/userteste/$usuario.sh now + $tempo hour > /dev/null 2>&1
EOF
	echo ${callback_query_from_id} >> lista
    # - ENVIA O SSH
    ShellBot.sendMessage --chat_id ${callback_query_message_chat_id} \
    --text "$(echo -e " <b>CREADO CON ÉXITO</b> \n\nIP: $ip_server3\nUSUARIO: <code>$usuario</code>\nCONTRASEÑA: <code>$senha</code>\n\n⏳ Expira em: $tempo Hora")" \
    --parse_mode html
    return 0
else
ShellBot.sendMessage --chat_id ${callback_query_message_chat_id} \
	--text "$(echo -e SERVIDOR INDISPONIBLE)" \
	--parse_mode html
	return 0
fi
}

#informacoes usuario
infouser () {
	ShellBot.sendMessage --chat_id ${message_chat_id[$id]} \
	--text "$(echo -e "Nome:  ${message_from_first_name[$(ShellBot.ListUpdates)]}\nUser: @${message_from_username[$(ShellBot.ListUpdates)]:-null}")\nID: ${message_from_id[$(ShellBot.ListUpdates)]} " \
	--parse_mode html
	return 0
}

unset botao1
botao1=''
ShellBot.InlineKeyboardButton --button 'botao1' --line 1 --text 'GENERAR CUENTA GRATIS' --callback_data 'gerarssh'
#ShellBot.InlineKeyboardButton --button 'botao1' --line 2 --text '🇨🇦 GENERAR SSH CA 01 🇨🇦' --callback_data 'gerarssh2'
ShellBot.InlineKeyboardButton --button 'botao1' --line 2 --text 'DESCARGAR MI APP' --callback_data '2' --url 'https://web.mscperu.store'
ShellBot.InlineKeyboardButton --button 'botao1' --line 3 --text 'TELEGRAM' --callback_data '3' --url 'https://t.me/MSCPERU'
ShellBot.InlineKeyboardButton --button 'botao1' --line 4 --text '⬇️ GRUPO TELEGRAM ⬇️' --callback_data '5' --url 'https://t.me/MSCPERU.'
ShellBot.regHandleFunction --function criarteste --callback_data gerarssh
ShellBot.regHandleFunction --function criarteste2 --callback_data gerarssh2
ShellBot.regHandleFunction --function criarteste3 --callback_data gerarssh3
unset keyboard1
keyboard1="$(ShellBot.InlineKeyboardMarkup -b 'botao1')"
while :; do
   [[ "$(date +%d)" != "$(cat RESET)" ]] && {
   	echo $(date +%d) > RESET
   	echo ' ' > lista
   }
  ShellBot.getUpdates --limit 100 --offset $(ShellBot.OffsetNext) --timeout 30
  for id in $(ShellBot.ListUpdates); do
    (
      ShellBot.watchHandle --callback_data ${callback_query_data[$id]}
      comando=(${message_text[$id]})
      [[ "${comando[0]}" = "/menu"  || "${comando[0]}" = "/start" ]] && menu
      [[ "${comando[0]}" = "/id"  ]] && infouser
    ) &
  done
done
