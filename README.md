# learning-zsh
This is a collection of snippets used in _Learning ZSH_ at LinkedIn Learning

## Random number guessing game:
```
r=$(( $RANDOM % 8 ))
echo "I'm thinking of a number between zero and eight. Can you guess it?"
vared -p "> " -c g
if [[ $g -eq $r ]]; then;
	echo "Congratulations, $r is correct!"
else;
	echo "Sorry, I was thinking of $r!"
fi
```

## Sample prompt strings
A colorful string: 
`PROMPT='[%F{164}%n%f@%F{135}%m%f %F{025}%d%f]%# '`

Another colorful string: 
`PROMPT='[%F{009}%n%f@%F{015}%m%f %F{027}%d%f]%# '`

Default string: 
`PROMPT=%m%#`

Right prompt showing the time: 
`RPROMPT=%*`

Right prompt showing the current working directory: 
`RPROMPT=$d`

Right prompt showing the collapsed user directory: 
`RPROMPT=%~`

Empty right prompt: 
`RPROMPT=''`

## Listing the prompt colors
Function to show 256 colors in the foreground (`%F`) and background (`%B`). Adapted from [the oh-my-zsh spectrum.zsh file](https://github.com/robbyrussell/oh-my-zsh/blob/master/lib/spectrum.zsh#L22).
```
function colors() {
  for color in {000..255}; do
    print -P "$color: %F{$color}████ Foreground %f%K{$color} Background %k"
  done
}
```

Right prompt showing the remaining battery percentage, the date, and time: 
`RPROMPT='$(battery_pct_prompt) @ %D %*'`
