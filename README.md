## Wake Boxes General Rule For Aerodynamic sims


Sizing and Placement Guidelines

Proper wakebox sizing balances drag/downforce accuracy against total cell count and solver runtime.
• Nest multiple boxes. Use a tight, high-resolution near-wake box immediately behind the body and a larger, coarser far-wake box downstream. Stepping down by one refinement level per box prevents abrupt 8:1 cell volume jumps that cause numerical diffusion.
• Start ahead of the trailing edge. Overlap the upstream face of the wakebox with the body itself rather than starting right at the rear bumper or trailing edge. This ensures smooth cell transitions where the boundary layer separates.
• Scale by characteristic length (L). For automotive or bluff-body aerodynamics, extend the near-wake box roughly 1 to 1.5 body lengths downstream and the far-wake box 3 to 5 body lengths downstream. Make the width and height 1.2 to 1.5 times the frontal projection to contain lateral vortex expansion.
• Align with nCellsBetweenLevels. Set nCellsBetweenLevels to at least 3 or 4 in castellatedMeshControls so snappyHexMesh creates buffer layers between your wakebox levels.
