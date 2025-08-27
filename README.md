# Im_something_of_a_paintermyself
Results and analysis
Public MiFID: submitted to Kaggle; see the included leaderboard screenshot for the score and rank.
Observations: Using a small pool of ~50 Monet reference images to guide color transfer produced more varied palettes and fewer strong color casts than using a single reference. Standardizing to 256×256 and exporting 7,000 flat JPGs (no subfolders) satisfied the competition requirements. JPEG quality 92 provided a good size/quality balance for the zip.
Troubleshooting: Ensured files were JPG (not PNG), exactly 7,000 images at 256×256, placed at the zip root. If Save Version failed, a one-cell generator created images.zip and the file was uploaded on the competition page.

Model comparison and simple tuning
Compared reference-pool size for the baseline: 1 Monet reference versus ~50 references. The ~50-reference setting reduced uniform color tints and improved visual diversity in the generated outputs. A full CycleGAN run is outlined but not executed in this submission due to time; planned settings are included in the notebook (ResNet-9 generators, 70×70 PatchGAN, losses: adversarial + cycle λ=10 + identity λ=5, Adam lr=2e-4, β1=0.5, batch 1–4).

Conclusion
Best result: color-transfer baseline with ~50 Monet references (7,000 JPGs @ 256×256) — see public MiFID on the leaderboard screenshot.
What I learned: fast color/tonal transfer yields a strong, reproducible baseline but cannot model Monet’s texture/brush strokes.
What didn’t work: single-reference transfer often created strong global color casts.
Next steps: train a lightweight CycleGAN with the hyperparameters listed above, compare MiFID and qualitative grids to the baseline, and explore small data augmentations during training.
