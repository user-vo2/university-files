Use -bf=1 vival option.  
You may also want to use valgrind (-vg option). It is not compatible with -fsanitize.  
If you see problems with linking, edit vival's `compiler.py`:
```py
subprocess.run([self._lang2compiler[self.guessed_lang].value] + self.flags + [str(main_obj), str(exec_obj), '-o', str(res_path)],
                           check=True)
```
Put this instead of line 93 (3.2.0)

#### UPD
Fixed in 3.2.1
