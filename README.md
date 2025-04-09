# awesome-nvim-keymaps
A collection of awesome neovim keymaps


Replace word under cursor
```lua
vim.keymap.set(
    "n",
    "<leader>rw",
    ":%s/\\<<C-r><C-w>\\>/<C-r><C-w>/gI<Left><Left><Left>",
    { noremap = true, silent = false, desc = "Replace word under cursor" }
)
```


Move visual selection up or down
```lua
vim.keymap.set("v", "J", ":m '>+1<CR>gv=gv", { silent = true })
vim.keymap.set("v", "K", ":m '<-2<CR>gv=gv", { silent = true })
```


Create undo breakpoints in insert mode
```lua
vim.keymap.set("i", ",", ",<c-g>u", { noremap = true, silent = true })
vim.keymap.set("i", ".", ".<c-g>u", { noremap = true, silent = true })
vim.keymap.set("i", "!", "!<c-g>u", { noremap = true, silent = true })
vim.keymap.set("i", "?", "?<c-g>u", { noremap = true, silent = true })
```

Binds window to <leader>+number, making it easier to move between windows
```lua
for i = 1, 6 do
    local lhs = "<leader>" .. i
    local rhs = i .. "<C-W>w"
    vim.keymap.set("n", lhs, rhs, { desc = "Move to window: " .. i })
end
```


Copies to clipboard
```lua
vim.keymap.set({ "n", "v" }, "<leader>y", '"+y')
```

Yanks to the end of the line
```lua
vim.keymap.set("n", "Y", "y$")
```

Pastes over selected text without changing your yank register
```lua
vim.keymap.set("x", "<leader>pv", '"_dP', silentOptions)
```

Resize windows
```lua
vim.keymap.set('n', '<C-Up>', ':resize +2<CR>', { silent = true, desc = "Increase window height" })
vim.keymap.set('n', '<C-Down>', ':resize -2<CR>', { silent = true, desc = "Decrease window height" })
vim.keymap.set('n', '<C-Left>', ':vertical resize -2<CR>', { silent = true, desc = "Decrease window width" })
vim.keymap.set('n', '<C-Right>', ':vertical resize +2<CR>', { silent = true, desc = "Increase window width" })
```
